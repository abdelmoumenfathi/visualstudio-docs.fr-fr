---
title: Élément OnError (MSBuild) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#OnError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- OnError Element [MSBuild]
- <OnError Element [MSBuild]
ms.assetid: 765767d3-ecb7-4cd9-ba1e-d9468964dddc
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 46f6907bea5954cffae92b41398717a8247350e0
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59667246"
---
# <a name="onerror-element-msbuild"></a>OnError, élément (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Provoque l’exécution d’une ou de plusieurs cibles si l’attribut `ContinueOnError` est défini sur `false` pour une tâche en échec.  
  
 \<Project>  
 \<Target>  
 \<OnError>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<OnError ExecuteTargets="TargetName"  
    Condition="'String A'=='String B'" />  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|`Condition`|Attribut facultatif.<br /><br /> Condition à évaluer. Pour plus d’informations, consultez l’article [Conditions (Conditions MSBuild)](../msbuild/msbuild-conditions.md).|  
|`ExecuteTargets`|Attribut requis.<br /><br /> Les cibles à exécuter si une tâche échoue. Séparez les cibles multiples avec des points-virgules. Les cibles multiples sont exécutées dans l’ordre spécifié.|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[Target](../msbuild/target-element-msbuild.md)|Élément conteneur des tâches [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)].|  
  
## <a name="remarks"></a>Remarques  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] exécute l’élément `OnError` si l’une des tâches de l’élément `Target` échoue avec l’attribut `ContinueOnError` défini sur `ErrorAndStop` (ou `false`). Lorsque la tâche échoue, les cibles spécifiées dans l’attribut `ExecuteTargets` sont exécutées. S’il existe plusieurs éléments `OnError` dans la cible, les éléments `OnError` sont exécutés séquentiellement lorsque la tâche échoue.  
  
 Pour plus d’informations sur l’attribut `ContinueOnError`, consultez l’article [Task Element (MSBuild) (Élément Task [MSBuild])](../msbuild/task-element-msbuild.md). Pour plus d’informations sur les cibles, consultez l’article [MSBuild Targets](../msbuild/msbuild-targets.md) (Cibles MSBuild).  
  
## <a name="example"></a>Exemple  
 Le code suivant exécute les tâches `TaskOne` et `TaskTwo`. Si `TaskOne` échoue, [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] évalue l’élément `OnError` et exécute la cible `OtherTarget`.  
  
```  
<Target Name="ThisTarget">  
    <TaskOne ContinueOnError="ErrorAndStop">  
    </TaskOne>  
    <TaskTwo>  
    </TaskTwo>  
    <OnError ExecuteTargets="OtherTarget" />  
</Target>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur le schéma de fichier projet MSBuild](../msbuild/msbuild-project-file-schema-reference.md)   
 [Cibles](../msbuild/msbuild-targets.md)
