---
title: Tâche Error | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Error
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Error task [MSBuild]
- MSBuild, Error task
ms.assetid: e96a90ee-a8ae-4e5b-8ef2-b5cf5fedd8b2
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a7579a448a113c51a58e492da6ea9e7e4ca9ede
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47501165"
---
# <a name="error-task"></a>Error, tâche
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [erreur tâche](https://docs.microsoft.com/visualstudio/msbuild/error-task).  
  
  
Arrête une génération et enregistre une erreur en fonction d’une instruction conditionnelle évaluée.  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche `Error`.  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Code`|Paramètre `String` facultatif.<br /><br /> Code d’erreur à associer à l’erreur.|  
|`File`|Paramètre `String` facultatif.<br /><br /> Nom du fichier qui contient l’erreur. Si aucun nom de fichier n’est fourni, le fichier contenant la tâche Error est utilisé.|  
|`HelpKeyword`|Paramètre `String` facultatif.<br /><br /> Mot clé d’aide à associer à l’erreur.|  
|`Text`|Paramètre `String` facultatif.<br /><br /> Texte d’erreur enregistré par [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] si le paramètre `Condition` a la valeur `true`.|  
  
## <a name="remarks"></a>Notes  
 La tâche `Error` permet aux projets [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] d’émettre un texte d’erreur dans les enregistreurs d’événements et d’arrêter l’exécution de la génération.  
  
 Si le paramètre `Condition` a la valeur `true`, la génération est arrêtée, et une erreur est enregistrée. Si un paramètre `Condition` n’existe pas, l’erreur est enregistrée, et l’exécution de la génération s’arrête. Pour plus d’informations sur la journalisation, consultez l’article [Obtention de journaux de génération avec MSBuild](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 En plus des paramètres énumérés ci-dessus, cette tâche hérite des paramètres de la classe <xref:Microsoft.Build.Tasks.TaskExtension>, qui elle-même hérite de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant vérifie que toutes les propriétés requises sont définies. Si elles ne le sont pas, le projet déclenche un événement d’erreur et enregistre la valeur du paramètre `Text` de la tâche `Error`.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="ValidateCommandLine">  
        <Error  
            Text=" The 0 property must be set on the command line."  
            Condition="'$(0)' == ''" />  
        <Error  
            Text="The FREEBUILD property must be set on the command line."  
            Condition="'$(FREEBUILD)' == ''" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des tâches](../msbuild/msbuild-task-reference.md)   
 [Obtention de journaux de génération avec MSBuild](../msbuild/obtaining-build-logs-with-msbuild.md)


