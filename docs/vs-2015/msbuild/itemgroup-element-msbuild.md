---
title: Élément ItemGroup (MSBuild) | Microsoft Docs
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
- http://schemas.microsoft.com/developer/msbuild/2003#ItemGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemGroup element [MSBuild]
- <ItemGroup> element [MSBuild]
ms.assetid: aac894e3-a9f1-4bbc-a796-6ef07001f35b
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c006d7622c8af76694618e828b014f695914fd58
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47503646"
---
# <a name="itemgroup-element-msbuild"></a>Élément ItemGroup (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [ItemGroup, élément (MSBuild)](https://docs.microsoft.com/visualstudio/msbuild/itemgroup-element-msbuild).  
  
  
Contient un ensemble d’éléments [Item](../msbuild/item-element-msbuild.md) définis par l’utilisateur. Chaque élément utilisé dans un projet [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] doit être spécifié en tant qu’enfant d’un élément `ItemGroup`.  
  
 \<Project>  
 \<ItemGroup>  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<ItemGroup Condition="'String A' == 'String B'">  
    <Item1>... </Item1>  
    <Item2>... </Item2>  
</ItemGroup>  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|`Condition`|Attribut facultatif. Condition à évaluer. Pour plus d’informations, consultez l’article [Conditions (Conditions MSBuild)](../msbuild/msbuild-conditions.md).|  
  
### <a name="child-elements"></a>Éléments enfants  
  
|Élément|Description|  
|-------------|-----------------|  
|[Item](../msbuild/item-element-msbuild.md)|Définit les entrées du processus de génération. Un élément `ItemGroup` peut ne contenir aucun élément `Item` ou en contenir plusieurs.|  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[Projet](../msbuild/project-element-msbuild.md)|Élément racine requis d'un fichier projet [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)].|  
|[Target](../msbuild/target-element-msbuild.md)|Depuis .NET Framework 3.5, l’élément `ItemGroup` peut apparaître dans un élément `Target`. Pour plus d’informations, consultez l’article [Targets (Cibles MSBuild)](../msbuild/msbuild-targets.md).|  
  
## <a name="remarks"></a>Notes  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant illustre les collections d’éléments définis par l’utilisateur `Res` et `CodeFiles` déclarés dans un élément `ItemGroup`. Chacun des éléments de la collection d’éléments `Res` contient un élément [ItemMetadata](../msbuild/itemmetadata-element-msbuild.md) enfant défini par l’utilisateur.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Res Include = "Strings.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include = "Dialogs.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
  
        <CodeFiles Include="**\*.cs" Exclude="**\generated\*.cs" />  
        <CodeFiles Include="..\..\Resources\Constants.cs" />  
    </ItemGroup>  
...  
</Project>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du schéma de fichier projet](../msbuild/msbuild-project-file-schema-reference.md)   
 [Éléments](../msbuild/msbuild-items.md)   
 [Éléments communs des projets MSBuild](../msbuild/common-msbuild-project-items.md)


