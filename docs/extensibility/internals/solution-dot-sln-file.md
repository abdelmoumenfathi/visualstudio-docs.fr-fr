---
title: Solution (. Fichier de sln)
ms.date: 03/15/2019
ms.topic: conceptual
helpviewer_keywords:
- sln files, VSPackages
- solutions, .sln files
- .sln files, VSPackages
ms.assetid: 7d7ef539-2e4b-4637-b853-8ec7626609df
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ee1a66cee2d42c0ef23b4d4b8441a3c0cda125c4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62908750"
---
# <a name="solution-sln-file"></a>Fichier solution (.sln)

Une solution est une structure pour organiser les projets dans Visual Studio. La solution gère les informations d’état pour les projets dans deux fichiers :

- fichier .sln (textuel, partagé)

- fichier .suo (options de la solution binaire, spécifiques à l’utilisateur)

Pour plus d’informations sur les fichiers .suo, consultez [Options utilisateur de Solution (. Fichier suo)](../../extensibility/internals/solution-user-options-dot-suo-file.md).

Si votre VSPackage est chargé à la suite référencé dans le fichier .sln, l’environnement appelle <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> pour lire le fichier .sln.

Le fichier .sln contient des informations textuelles que l’environnement utilise pour rechercher et charger les paramètres nom-valeur pour les données persistantes et le projet VSPackages elle fait référence. Lorsqu’un utilisateur ouvre une solution, l’environnement parcourt le `preSolution`, `Project`, et `postSolution` informations dans le fichier .sln pour charger la solution, des projets dans la solution et toutes les informations persistantes attaché à la solution.

Chaque fichier de projet contient des informations supplémentaires lues par l’environnement pour remplir la hiérarchie avec les éléments de ce projet. La persistance de données de hiérarchie est contrôlée par le projet. Les données ne sont normalement pas stockées dans le fichier .sln, bien que vous pouvez intentionnellement écrire des informations sur le projet dans le fichier .sln, si vous choisissez de faire. Pour plus d’informations sur la persistance, consultez [persistance d’un projet](../../extensibility/internals/project-persistence.md) et [d’ouverture et de l’enregistrement des éléments de projet](../../extensibility/internals/opening-and-saving-project-items.md).

## <a name="file-header"></a>En-tête du fichier

L’en-tête d’un fichier .sln ressemble à ceci :

::: moniker range="vs-2017"

```
Microsoft Visual Studio Solution File, Format Version 12.00
# Visual Studio 15
VisualStudioVersion = 15.0.26730.15
MinimumVisualStudioVersion = 10.0.40219.1
```

### <a name="definitions"></a>Définitions

`Microsoft Visual Studio Solution File, Format Version 12.00`\
En-tête standard qui définit la version de format de fichier.

`# Visual Studio 15`\
La version principale de Visual Studio (plus récemment) enregistré ce fichier de solution. Ces informations contrôlent le numéro de version dans l’icône de solution.

`VisualStudioVersion = 15.0.26730.15`\
La version complète de Visual Studio (plus récemment) enregistré le fichier de solution. Si le fichier solution est enregistré par une version plus récente de Visual Studio qui a la même version principale, cette valeur n’est pas mis à jour afin de réduire le taux d’activité dans les fichiers de solution.

`MinimumVisualStudioVersion = 10.0.40219.1`\
La version minimale (la plus ancienne) de Visual Studio qui peut ouvrir ce fichier de solution.

::: moniker-end

::: moniker range=">=vs-2019"

```
Microsoft Visual Studio Solution File, Format Version 12.00
# Visual Studio Version 16
VisualStudioVersion = 16.0.28701.123
MinimumVisualStudioVersion = 10.0.40219.1
```

### <a name="definitions"></a>Définitions

`Microsoft Visual Studio Solution File, Format Version 12.00`\
En-tête standard qui définit la version de format de fichier.

`# Visual Studio Version 16`\
La version principale de Visual Studio (plus récemment) enregistré ce fichier de solution. Ces informations contrôlent le numéro de version dans l’icône de solution.

`VisualStudioVersion = 16.0.28701.123`\
La version complète de Visual Studio (plus récemment) enregistré le fichier de solution. Si le fichier solution est enregistré par une version plus récente de Visual Studio qui a la même version principale, cette valeur n’est pas mis à jour afin de réduire le taux d’activité dans le fichier.

`MinimumVisualStudioVersion = 10.0.40219.1`\
La version minimale (la plus ancienne) de Visual Studio qui peut ouvrir ce fichier de solution.

::: moniker-end

## <a name="file-body"></a>Corps du fichier

Le corps d’un fichier .sln se compose de plusieurs sections libellées `GlobalSection`, comme suit :

```
Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1", "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}"
EndProject
Global
  GlobalSection(SolutionNotes) = postSolution
  EndGlobalSection
  GlobalSection(SolutionConfiguration) = preSolution
       ConfigName.0 = Debug
       ConfigName.1 = Release
  EndGlobalSection
  GlobalSection(ProjectDependencies) = postSolution
  EndGlobalSection
  GlobalSection(ProjectConfiguration) = postSolution
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.ActiveCfg = Debug|x86
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Debug.Build.0 = Debug|x86
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.ActiveCfg = Release|x86
   {8CDD8387-B905-44A8-B5D5-07BB50E05BEA}.Release.Build.0 = Release|x86
  EndGlobalSection
  GlobalSection(ExtensibilityGlobals) = postSolution
  EndGlobalSection
  GlobalSection(ExtensibilityAddIns) = postSolution
  EndGlobalSection
EndGlobal
```

Pour charger une solution, l’environnement exécute la séquence de tâches suivante :

1. L’environnement lit la section globale du fichier .sln et traite toutes les sections marquées `preSolution`. Dans cet exemple de fichier, il existe une telle instruction :

   ```
   GlobalSection(SolutionConfiguration) = preSolution
        ConfigName.0 = Debug
        ConfigName.1 = Release
   ```

   Lorsque l’environnement lit le `GlobalSection('name')` balise, il mappe le nom à un VSPackage à l’aide du Registre. Le nom de clé doit exister dans le Registre sous [HKLM\\< Registre racine de l’ID d’Application\>\SolutionPersistence\AggregateGUIDs]. Des clés par défaut est le GUID de Package (REG_SZ) du VSPackage qui a écrit les entrées.

2. L’environnement charge le VSPackage, appels `QueryInterface` sur le VSPackage pour la <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> interface et appelle le <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.ReadSolutionProps%2A> méthode avec les données dans la section afin que le VSPackage peut stocker les données. L’environnement répète ce processus pour chaque `preSolution` section.

3. L’environnement effectue une itération dans les blocs de persistance du projet. Dans ce cas, il existe un projet.

   ```
   Project("{F184B08F-C81C-45F6-A57F-5ABD9991F28F}") = "Project1",
   "Project1.vbproj", "{8CDD8387-B905-44A8-B5D5-07BB50E05BEA}"
   EndProject
   ```

   Cette instruction contient le GUID du projet unique et le GUID du type de projet. Ces informations sont utilisées par l’environnement pour rechercher le fichier projet ou les fichiers appartenant à la solution, et le VSPackage est requis pour chaque projet. Le projet GUID est passé à <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> pour charger le VSPackage spécifique associé au projet, puis le projet est chargé par le VSPackage. Dans ce cas, le VSPackage est chargé pour ce projet est Visual Basic.

   Chaque projet peut conserver un ID d’instance unique du projet afin qu’il soit accessible en fonction des besoins par d’autres projets dans la solution. Dans l’idéal, si la solution et les projets sont sous contrôle de code source, le chemin d’accès au projet doit être le chemin d’accès à la solution. Lors du premier chargement de la solution, les fichiers de projet ne peut pas être sur l’ordinateur de l’utilisateur. Lorsque le fichier de projet stocké sur le serveur relatif au fichier de solution, il est relativement simple pour le fichier projet pour trouver et copiés vers l’ordinateur de l’utilisateur. Il copie et charge le reste des fichiers nécessaires pour le projet.

4. Selon les informations contenues dans la section de projet du fichier .sln, l’environnement charge chaque fichier de projet. Le projet lui-même est alors chargé de remplissage de la hiérarchie de projet et le chargement de tous les projets imbriqués.

5. Après le traitement de toutes les sections du fichier .sln, la solution s’affiche dans l’Explorateur de solutions et est prête pour la modification par l’utilisateur.

Si un VSPackage qui implémente un projet dans la solution ne parvient pas à charger, le <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.OnProjectLoadFailure%2A> méthode est appelée et tous les autres projets dans la solution sont la possibilité d’ignorer les modifications peuvent avoir pendant le chargement. En cas d’erreurs d’analyse, autant d’informations que possible est conservé avec les fichiers solution et l’environnement affiche une boîte de dialogue avertit l’utilisateur que la solution est endommagée.

Lorsque la solution est enregistrée ou fermée, le <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.QuerySaveSolutionProps%2A> méthode est appelée et transmise à la hiérarchie pour voir si des modifications ont été apportées à la solution qui doivent être entrés dans le fichier .sln. Une valeur null transmise à `QuerySaveSolutionProps` dans <xref:Microsoft.VisualStudio.Shell.Interop.VSQUERYSAVESLNPROPS>, indique que des informations en cours sont rendue persistante pour la solution. Si la valeur n’est pas null, les informations persistantes sont pour un projet spécifique, déterminé par le pointeur vers le <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> interface.

S’il existe des informations à enregistrer, le <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> interface est appelée avec un pointeur vers le <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.SaveSolutionProps%2A> (méthode). Le <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps.WriteSolutionProps%2A> méthode est ensuite appelée par l’environnement pour récupérer les paires nom-valeur à partir de `IPropertyBag` interface et écrire les informations dans le fichier .sln.

`SaveSolutionProps` et `WriteSolutionProps` objets sont appelées de manière récursive par l’environnement pour récupérer des informations à enregistrer à partir de la `IPropertyBag` interface jusqu'à ce que toutes les modifications ont été entrées dans le fichier .sln. De cette façon, vous pouvez vous assurer que les informations sont rendues persistantes avec la solution et la prochaine disponible, que la solution est ouverte.

Chaque VSPackage chargé est énumérée pour voir s’il n’a rien à enregistrer dans le fichier .sln. Il est uniquement au moment du chargement que les clés de Registre sont interrogées. L’environnement connaît tous les packages chargés, car elles se trouvent dans la mémoire au moment de que l’enregistrement de la solution.

Seul le fichier .sln contient des entrées dans le `preSolution` et `postSolution` sections. Il n’existe aucune section similaire dans le fichier .suo dans la mesure où la solution a besoin de ces informations pour charger correctement. Le fichier .suo contient les options spécifiques à l’utilisateur, telles que des notes privés, qui ne sont pas destinées à être partagés ou placés sous contrôle de code source.

## <a name="see-also"></a>Voir aussi

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>
- [Fichiers des options utilisateur de solution (.Suo)](../../extensibility/internals/solution-user-options-dot-suo-file.md)
- [Solutions](../../extensibility/internals/solutions-overview.md)