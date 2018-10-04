---
title: 'CA2235 : Marquez tous les champs non sérialisables | Microsoft Docs'
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
- CA2235
- MarkAllNonSerializableFields
helpviewer_keywords:
- CA2235
- MarkAllNonSerializableFields
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 025ee336052bdad010b55e1ba804b2bd37c7e0d7
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589802"
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235 : Marquez tous les champs non sérialisés
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [CA2235 : Marquez tous les champs non sérialisables](https://docs.microsoft.com/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields).

|||
|-|-|
|TypeName|MarkAllNonSerializableFields|
|CheckId|CA2235|
|Category|Microsoft.Usage|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Un champ d'instance d'un type non sérialisable est déclaré dans un type sérialisable.

## <a name="rule-description"></a>Description de la règle
 Un type sérialisable est celui qui est marqué avec le <xref:System.SerializableAttribute?displayProperty=fullName> attribut. Lorsque le type est sérialisé, une <xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> exception est levée si un type contient un champ d’instance d’un type qui n’est pas sérialisable.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, appliquez le <xref:System.NonSerializedAttribute?displayProperty=fullName> attribut au champ qui n’est pas sérialisable.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimez uniquement un avertissement de cette règle si un <xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName> type est déclaré qui permet aux instances du champ à être sérialisées et désérialisées.

## <a name="example"></a>Exemple
 L’exemple suivant montre un type qui viole la règle et un type qui satisfait la règle.

 [!code-csharp[FxCop.Usage.MarkNonSerializable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkNonSerializable/cs/FxCop.Usage.MarkNonSerializable.cs#1)]
 [!code-vb[FxCop.Usage.MarkNonSerializable#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkNonSerializable/vb/FxCop.Usage.MarkNonSerializable.vb#1)]

## <a name="related-rules"></a>Règles associées
 [CA2236 : Appelez les méthodes de la classe de base sur les types ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240 : Implémentez ISerializable correctement](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229 : Implémentez des constructeurs de sérialisation](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238 : Implémentez les méthodes de sérialisation correctement](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2237 : Marquez les types ISerializable avec SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239 : Spécifiez des méthodes de désérialisation pour les champs facultatifs](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120 : Sécurisez les constructeurs de sérialisation](../code-quality/ca2120-secure-serialization-constructors.md)


