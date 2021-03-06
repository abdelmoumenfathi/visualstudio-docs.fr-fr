---
title: 'Procédure : Substituer des paramètres dans un modèle | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- template parameters, substituting
- Visual Studio templates, using parameters
ms.assetid: a62924a7-4ba0-413d-b606-fdbe1fcf2807
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3c0a710bc3ad504c6654528db33b9a6698f4f7ae
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435159"
---
# <a name="how-to-substitute-parameters-in-a-template"></a>Procédure : Substituer des paramètres dans un modèle
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez remplacer les paramètres d'un modèle, tels que les noms de classes et les espaces de noms, lors de la création d'un fichier basé sur ce modèle. Pour obtenir une liste exhaustive des paramètres de modèle, consultez [Paramètres de modèle](../ide/template-parameters.md).  
  
## <a name="procedure"></a>Procédure  
 Vous pouvez remplacer des paramètres dans les fichiers d'un modèle chaque fois qu'un projet basé sur ce modèle est créé. Cette procédure explique comment créer un modèle qui remplace le nom d'un espace de noms par le nom du projet sécurisé quand un projet est créé avec le modèle.  
  
#### <a name="to-use-a-parameter-to-replace-namespace-name-with-the-project-name"></a>Pour remplacer le nom de l'espace de noms par le nom du projet à l'aide d'un paramètre  
  
1. Ajoutez le paramètre dans l'un ou plusieurs des fichiers de code du modèle. Exemple :  
  
    ```  
    namespace $safeprojectname$  
    ```  
  
    > [!NOTE]
    > Les paramètres d’un modèle s’écrivent au format $*parameter*$.  
  
2. Dans le fichier .vstemplate du modèle, localisez l'élément `ProjectItem` qui inclut ce fichier.  
  
3. Définissez l'attribut `ReplaceParameters` à la valeur `true` pour l'élément `ProjectItem`. Exemple :  
  
    ```  
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 [Création de modèles de projet et d’élément](../ide/creating-project-and-item-templates.md)   
 [Paramètres de modèle](../ide/template-parameters.md)   
 [Référence du schéma de modèle Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Élément ProjectItem (modèles d'élément Visual Studio)](../extensibility/projectitem-element-visual-studio-item-templates.md)
