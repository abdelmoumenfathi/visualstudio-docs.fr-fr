---
title: Fonctions d’élément | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- msbuild, Item functions
ms.assetid: 5e6df3cc-2db8-4cbd-8fdd-3ffd03ac0876
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d01de837deb5141b4b0bdbb7bebcb50412826b1f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63007003"
---
# <a name="item-functions"></a>fonctions d'élément
À compter de MSBuild 4.0, le code dans les tâches et les cibles peut appeler des fonctions d’élément pour obtenir des informations sur les éléments du projet. Ces fonctions simplifient l’obtention des éléments Distinct() et sont plus rapides que l’exécution d’une boucle dans les éléments.

## <a name="string-item-functions"></a>Fonctions d’élément de type chaîne
Vous pouvez utiliser des méthodes et des propriétés de chaîne dans le .NET Framework pour manipuler n’importe quelle valeur d’élément. Pour les méthodes <xref:System.String>, spécifiez le nom de la méthode. Pour les propriétés <xref:System.String>, spécifiez le nom de la propriété après « get_ ».

Pour les éléments qui ont plusieurs chaînes, la méthode ou la propriété de chaîne s’exécute sur chaque chaîne.

L’exemple suivant montre comment utiliser ces méthodes d’élément de type chaîne.

```xml
<ItemGroup>
    <theItem Include="andromeda;tadpole;cartwheel" />
</ItemGroup>

<Target Name = "go">
    <Message Text="IndexOf  @(theItem->IndexOf('r'))" />
    <Message Text="Replace  @(theItem->Replace('tadpole', 'pinwheel'))" />
    <Message Text="Length   @(theItem->get_Length())" />
    <Message Text="Chars    @(theItem->get_Chars(2))" />
</Target>

  <!--
  Output:
    IndexOf  3;-1;2
    Replace  andromeda;pinwheel;cartwheel
    Length   9;7;9
    Chars    d;d;r
  -->
```

## <a name="intrinsic-item-functions"></a>Fonctions d’élément intrinsèques
Le tableau ci-dessous liste les fonctions intrinsèques disponibles pour les éléments.

|Fonction|Exemple|Description|
|--------------|-------------|-----------------|
|`Count`|`@(MyItem->Count())`|Retourne le nombre d’éléments.|
|`DirectoryName`|`@(MyItem->DirectoryName())`|Retourne l’équivalent de `Path.DirectoryName` pour chaque élément.|
|`Distinct`|`@(MyItem->Distinct())`|Retourne les éléments qui ont des valeurs `Include` distinctes. Les métadonnées sont ignorées. La comparaison ne respecte pas la casse.|
|`DistinctWithCase`|`@(MyItem->DistinctWithCase())`|Retourne les éléments qui ont des valeurs `itemspec` distinctes. Les métadonnées sont ignorées. La comparaison respecte la casse.|
|`Reverse`|`@(MyItem->Reverse())`|Retourne les éléments en ordre inverse.|
|`AnyHaveMetadataValue`|`@(MyItem->AnyHaveMetadataValue("MetadataName", "MetadataValue"))`|Retourne un `boolean` pour indiquer si un élément a le nom et la valeur des métadonnées fournies. La comparaison ne respecte pas la casse.|
|`ClearMetadata`|`@(MyItem->ClearMetadata())`|Retourne les éléments avec leurs métadonnées effacées. Seul `itemspec` est conservé.|
|`HasMetadata`|`@(MyItem->HasMetadata("MetadataName"))`|Retourne les éléments qui ont le nom des métadonnées fourni. La comparaison ne respecte pas la casse.|
|`Metadata`|`@(MyItem->Metadata("MetadataName"))`|Retourne les valeurs des métadonnées qui ont le nom des métadonnées.|
|`WithMetadataValue`|`@(MyItem->WithMetadataValue("MetadataName", "MetadataValue"))`|Retourne les éléments qui ont le nom et la valeur des métadonnées fournis. La comparaison ne respecte pas la casse.|

L’exemple suivant montre comment utiliser des fonctions d’élément intrinsèques.

```xml
<ItemGroup>
    <TheItem Include="first">
        <Plant>geranium</Plant>
    </TheItem>
    <TheItem Include="second">
        <Plant>algae</Plant>
    </TheItem>
    <TheItem Include="third">
        <Plant>geranium</Plant>
    </TheItem>
</ItemGroup>

<Target Name="go">
    <Message Text="MetaData:    @(TheItem->Metadata('Plant'))" />
    <Message Text="HasMetadata: @(theItem->HasMetadata('Plant'))" />
    <Message Text="WithMetadataValue: @(TheItem->WithMetadataValue('Plant', 'geranium'))" />
    <Message Text=" " />
    <Message Text="Count:   @(theItem->Count())" />
    <Message Text="Reverse: @(theItem->Reverse())" />
</Target>

  <!--
  Output:
    MetaData:    geranium;algae;geranium
    HasMetadata: first;second;third
    WithMetadataValue: first;third

    Count:   3
    Reverse: third;second;first
  -->
```

## <a name="see-also"></a>Voir aussi
- [Éléments](../msbuild/msbuild-items.md)
