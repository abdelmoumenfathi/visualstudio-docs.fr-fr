---
title: 'CA2227 : Les propriétés de Collection doivent être en lecture seule | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c9c91a0e563c7e83157dcff06e982c1bda40c5b5
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47588090"
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227 : Les propriétés de collection doivent être en lecture seule
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [CA2227 : les propriétés de Collection doivent être en lecture seule](https://docs.microsoft.com/visualstudio/code-quality/ca2227-collection-properties-should-be-read-only).

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|Category|Microsoft.Usage|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Une propriété accessible en écriture extérieurement visible est un type qui implémente <xref:System.Collections.ICollection?displayProperty=fullName>. Tableaux, les indexeurs (propriétés portant le nom 'Item') et les jeux d’autorisations sont ignorés par la règle.

## <a name="rule-description"></a>Description de la règle
 Une propriété de collection accessible en écriture permet à un utilisateur de remplacer la collection par une collection complètement différente. Une propriété en lecture seule empêche le remplacement de la collection, mais permet quand même aux membres individuels d’être définis. Si le remplacement de la collection est un objectif, le modèle de conception préconisée consiste à inclure une méthode pour supprimer tous les éléments de la collection et une méthode pour remplir de nouveau la collection. Consultez le <xref:System.Collections.ArrayList.Clear%2A> et <xref:System.Collections.ArrayList.AddRange%2A> méthodes de la <xref:System.Collections.ArrayList?displayProperty=fullName> classe pour obtenir un exemple de ce modèle.

 Binaire et sérialisation XML prend en charge les propriétés en lecture seule qui sont des collections. Le <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> classe a des exigences spécifiques pour les types qui implémentent <xref:System.Collections.ICollection> et <xref:System.Collections.IEnumerable?displayProperty=fullName> afin d’être sérialisable.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, définissez la propriété en lecture seule et, si la conception exige, ajouter des méthodes pour effacer et de remplir à nouveau la collection.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant illustre un type avec une propriété de collection accessible en écriture et montre comment la collection peut être remplacée directement. En outre, la meilleure manière de remplacer une propriété de collection en lecture seule à l’aide `Clear` et `AddRange` méthodes s’affiche.

 [!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/cpp/FxCop.Usage.PropertiesReturningCollections.cpp#1)]
 [!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/cs/FxCop.Usage.PropertiesReturningCollections.cs#1)]
 [!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/vb/FxCop.Usage.PropertiesReturningCollections.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA1819 : Les propriétés ne doivent pas retourner des tableaux](../code-quality/ca1819-properties-should-not-return-arrays.md)


