---
title: Localiser les modèles
ms.date: 01/02/2018
ms.topic: conceptual
helpviewer_keywords:
- project templates [Visual Studio], locations
- item templates [Visual Studio], locations
- template locations [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: db74d23cf42e371f00bf25c7edcd8c480f7649d4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62430274"
---
# <a name="how-to-locate-and-organize-project-and-item-templates"></a>Procédure : Localiser et organiser des modèles de projet et d’élément

Les fichiers de modèle doivent être placés dans un emplacement connu pour être affichés dans les boîtes de dialogue Nouveau projet et Nouvel élément.

::: moniker range="vs-2017"

Vous pouvez également créer des sous-catégories personnalisées à l’emplacement du modèle utilisateur, et les catégories apparaissent dans les boîtes de dialogue **Nouveau projet** et **Ajouter un nouvel élément**.

::: moniker-end

## <a name="locate-templates"></a>Localiser les modèles

Les modèles installés et les modèles utilisateur sont stockés à deux emplacements différents.

### <a name="installed-templates"></a>Modèles installés

Par défaut, les modèles installés avec Visual Studio se trouvent dans :

::: moniker range="vs-2017"

- *%ProgramFiles(x86)%\\Microsoft Visual Studio\\2017\\\<édition>\\Common7\IDE\ProjectTemplates\\<Langage\>\\<ID_paramètres_régionaux\>*

- *%ProgramFiles(x86)%\\Microsoft Visual Studio\\2017\\\<édition>\Common7\IDE\ItemTemplates\\<Langage\>\\<ID_paramètres_régionaux\>*

Par exemple, le répertoire suivant contient les modèles d’élément Visual Basic pour le français (LCID 1036) :

*C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Community\\Common7\\IDE\\ItemTemplates\\VisualBasic\\1033*

::: moniker-end

::: moniker range=">=vs-2019"

- *%ProgramFiles(x86)%\\Microsoft Visual Studio\\2019\\\<édition>\\Common7\IDE\ProjectTemplates\\<Langage\>\\<ID_paramètres_régionaux\>*

- *%ProgramFiles(x86)%\\Microsoft Visual Studio\\2019\\\<édition>\Common7\IDE\ItemTemplates\\<Langage\>\\<ID_paramètres_régionaux\>*

Par exemple, le répertoire suivant contient les modèles d’élément Visual Basic pour le français (LCID 1036) :

*C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\Community\\Common7\\IDE\\ItemTemplates\\VisualBasic\\1033*

::: moniker-end

### <a name="user-templates"></a>Modèles utilisateur

Si vous ajoutez un fichier compressé (*.zip*) incluant un fichier *.vstemplate* au répertoire des modèles utilisateur, le modèle apparaît dans la boîte de dialogue Nouveau projet ou Nouvel élément. Par défaut, les modèles utilisateur se trouvent dans :

::: moniker range="vs-2017"

- *%USERPROFILE%\Documents\Visual Studio 2017\Templates\ProjectTemplates*

- *%USERPROFILE%\Documents\Visual Studio 2017\Templates\ItemTemplates*

Par exemple, le répertoire suivant contient les modèles de projet utilisateur pour C# :

- *C:\Users\UserName\Documents\Visual Studio 2017\Templates\ProjectTemplates\Visual C#*

::: moniker-end

::: moniker range=">=vs-2019"

- *%USERPROFILE%\Documents\Visual Studio 2019\Templates\ProjectTemplates*

- *%USERPROFILE%\Documents\Visual Studio 2019\Templates\ItemTemplates*

Par exemple, le répertoire suivant contient les modèles de projet utilisateur pour C# :

- *C:\Users\UserName\Documents\Visual Studio 2019\Templates\ProjectTemplates\Visual C#*

::: moniker-end

> [!TIP]
> Vous pouvez changer l’emplacement connu des modèles utilisateur dans **Outils** > **Options** > **Projets et solutions** > **Emplacements**.

::: moniker range="vs-2017"

## <a name="organize-templates"></a>Organiser les modèles

Les catégories des boîtes de dialogue **Nouveau projet** et **Ajouter un nouvel élément** reflètent les structures de répertoires qui existent aux emplacements des modèles installés et utilisateur. Pour organiser les modèles utilisateur dans leurs propres catégories, ajoutez de nouveaux dossiers au répertoire du modèle utilisateur. Les boîtes de dialogue **Nouveau projet** et **Ajouter un nouvel élément** montrent les changements que vous apportez à vos catégories de modèle utilisateur.

> [!NOTE]
> Vous ne pouvez pas créer de catégorie au niveau du langage de programmation. Vous ne pouvez créer une catégorie qu'à l'intérieur de chaque langage.

### <a name="create-new-user-project-template-categories"></a>Créer des catégories de modèles de projet utilisateur

1. Créez un sous-dossier dans le dossier du langage de programmation du répertoire des modèles de projet utilisateur. Par exemple, pour créer une catégorie **HelloWorld** pour les modèles de projet C#, créez le répertoire suivant :

    - *\%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ProjectTemplates\Visual C#\HelloWorld*

1. Placez tous les modèles de cette catégorie dans le nouveau dossier.

1. Dans le menu **Fichier**, choisissez **Nouveau** > **Projet**.

   La catégorie **HelloWorld** apparaît dans la boîte de dialogue **Nouveau projet**, sous **Installé** > **Visual C#**.

### <a name="create-new-user-item-template-categories"></a>Créer des catégories de modèles d’élément utilisateur

1. Créez un sous-dossier dans le dossier du langage de programmation du répertoire des modèles d’élément utilisateur. Par exemple, pour créer une catégorie **HelloWorld** pour les modèles d’élément C#, créez le répertoire suivant :

    - *\%USERPROFILE%\Documents\Visual Studio \<Version\>\Templates\ItemTemplates\Visual C#\HelloWorld*

1. Placez tous les modèles de cette catégorie dans le nouveau dossier.

1. Créez un projet ou ouvrez un projet existant. Ensuite, dans le menu **Projet**, choisissez **Ajouter un nouvel élément**.

   La catégorie **HelloWorld** apparaît dans la boîte de dialogue **Ajouter un nouvel élément**, sous **Installé** > **Éléments Visual C#**.

### <a name="display-templates-in-parent-categories"></a>Afficher les modèles dans les catégories parentes

Vous pouvez permettre l’affichage des modèles des sous-catégories dans leur catégorie parente à l’aide de l’élément `NumberOfParentCategoriesToRollUp` du fichier *.vstemplate*. Ces étapes sont les mêmes pour les modèles de projet et les modèles d’élément.

1. Localisez le fichier *.zip* qui contient le modèle.

1. Extrayez le fichier *.zip*.

1. Ouvrez le fichier *.vstemplate* dans Visual Studio.

1. Dans l'élément `TemplateData`, ajoutez un élément `NumberOfParentCategoriesToRollUp`. Par exemple, le code suivant fait apparaître le modèle dans sa catégorie parente, mais pas plus haut dans la hiérarchie.

    ```xml
    <TemplateData>
        ...
        <NumberOfParentCategoriesToRollUp>
            1
        </NumberOfParentCategoriesToRollUp>
        ...
    </TemplateData>
    ```

1. Enregistrez et fermez le fichier *.vstemplate*.

1. Sélectionnez les fichiers inclus dans votre modèle, cliquez avec le bouton droit sur la sélection, puis choisissez **Envoyer vers** > **Dossier compressé**.

   Les fichiers sont compressés dans un fichier *.zip*.

1. Supprimez les fichiers de modèles extraits et l’ancien fichier *.zip* de modèle.

1. Placez le nouveau fichier *.zip* dans le répertoire qui contenait le fichier *.zip* supprimé.

::: moniker-end

## <a name="see-also"></a>Voir aussi

- [Personnaliser les modèles](../ide/customizing-project-and-item-templates.md)
- [Informations de référence sur les schémas de modèles Visual Studio (extensibilité)](../extensibility/visual-studio-template-schema-reference.md)
- [NumberOfParentCategoriesToRollUp (modèles Visual Studio)](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)
- [Guide pratique pour créer des modèles de projet](../ide/how-to-create-project-templates.md)
- [Guide pratique pour créer des modèles d’élément](../ide/how-to-create-item-templates.md)