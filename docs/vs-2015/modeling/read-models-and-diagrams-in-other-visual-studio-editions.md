---
title: Lire des modèles et des diagrammes dans d’autres éditions de Visual Studio | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- models, versions of Visual Studio
ms.assetid: 46eee279-a9e4-4742-a024-5bd2cf032b86
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 21dc0cb7f02639ca6faa89ae4c067f21e083d6d3
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63387498"
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>Lire des modèles et des diagrammes dans d'autres éditions de Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Quand vous ouvrez un modèle dans une version de Visual Studio qui ne prend pas en charge la création de modèle, le modèle s'ouvre en mode lecture seule. Dans ce mode, vous pouvez modifier la disposition des diagrammes, mais vous ne pouvez pas modifier le modèle.  
  
 Pour connaître les versions de Visual Studio prennent en charge la création de modèles, consultez [versions prises en charge pour l’architecture et les outils de modélisation](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="obtaining-access-to-a-model-and-diagrams"></a>Obtention de l'accès à un modèle et à des diagrammes  
 Pour lire un diagramme UML ou un diagramme de couche, vous devez tout d’abord utiliser Visual Studio pour ouvrir le projet de modélisation et puis ouvrez le schéma qu’il contient.  
  
 Pour cette raison, si vous souhaitez lire un diagramme UML ou un diagramme de couche, vous devez aussi avoir accès au projet de modélisation dans lequel il a été créé. Pour cela, vous pouvez soit accéder au projet à partir de [!INCLUDE[esprscc](../includes/esprscc-md.md)], soit obtenir une copie des fichiers du projet.  
  
> [!NOTE]
> Cela ne s'applique pas aux cartes de code et aux diagrammes de classe .NET générés à partir du code. Ces diagrammes peuvent être affichés indépendamment d'un projet de modélisation.  
  
 Pour lire un diagramme UML ou un diagramme de couche, l'ensemble minimal de fichiers dont vous avez besoin est le suivant :  
  
- Les deux fichiers de diagrammes pour le diagramme que vous souhaitez lire, par exemple, **MyDiagram.classdiagram and MyDiagram.classdiagram.layout**.  
  
    > [!NOTE]
    > Des diagrammes de couche, vous devez également avoir le fichier nommé _Mondiagramme_**. layerdiagram.suppressions**.  
  
- Fichier de projet de modélisation (**MyModel.modelproj**)  
  
- Le fichier de modèle racine (**ModelDefinition\MyModel.uml**)  
  
- Les fichiers de package pour tout package référencé dans le diagramme (**ModelDefinition\MyPackage.UML**)  
  
## <a name="changes-that-you-can-make-in-read-only-mode"></a>Modifications que vous pouvez apporter en mode lecture seule  
 Si vous ouvrez un modèle et ses diagrammes dans une version de Visual Studio qui ne prend pas en charge la création de modèles, vous ne pouvez pas modifier le modèle. Autrement dit, vous ne pouvez pas modifier les éléments et les relations qui sont affichés dans les diagrammes ou dans l'Explorateur de modèles. En revanche, vous pouvez apporter certaines modifications à la disposition des diagrammes. Vous pouvez :  
  
- réorganiser les formes et connecteurs dans le diagramme ;  
  
- développer et réduire des formes.  
  
  Vous pouvez enregistrer ces modifications. Si vous souhaitez rendre visibles à d’autres utilisateurs vos modifications, vous devez envoyer au moins la mise à jour **.layout** fichiers.  
  
## <a name="RelatedTopics"></a> Rubriques connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Diagrammes de couche : Informations de référence](../modeling/layer-diagrams-reference.md)|Un diagramme de couche montre la structure d'une architecture existante ou proposée. Quand du code est écrit, il peut être validé automatiquement par rapport à un diagramme de couche.|  
|[Diagrammes d’activités UML : Informations de référence](../modeling/uml-activity-diagrams-reference.md)|Un diagramme d'activités montre un flux de travail dans un processus d'entreprise ou un logiciel.|  
|[Diagrammes de classes UML : Informations de référence](../modeling/uml-class-diagrams-reference.md)|Un diagramme de classes montre les types et les relations utilisés dans de nombreux contextes tels que le code, les schémas de base de données, les protocoles de communication ou le glossaire des termes employés pour décrire un domaine d'entreprise.|  
|[Diagrammes de composants UML : Informations de référence](../modeling/uml-component-diagrams-reference.md)|Un diagramme de composants montre les parties séparables dans une conception de logiciel, ainsi que leurs interfaces.|  
|[Diagrammes de séquence UML : Informations de référence](../modeling/uml-sequence-diagrams-reference.md)|Un diagramme de séquence montre les interactions entre des éléments dans une conception de logiciel.|  
|[Diagrammes de cas d’usage UML : Informations de référence](../modeling/uml-use-case-diagrams-reference.md)|Un diagramme de cas d'usage montre les utilisateurs d'un système et les activités qu'ils peuvent effectuer pour atteindre des objectifs spécifiques.|  
  
## <a name="see-also"></a>Voir aussi  
 [Créer des modèles pour votre application](../modeling/create-models-for-your-app.md)
