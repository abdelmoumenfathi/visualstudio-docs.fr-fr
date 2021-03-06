---
title: 'CA1039 : Les listes sont fortement typées | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1039
- ListsAreStronglyTyped
helpviewer_keywords:
- CA1039
- ListsAreStronglyTyped
ms.assetid: 5ac366c4-fd87-4d5c-95d5-f755510c8e5c
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3fb1a6255539ded989c5ad9638fc961d606a19f7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62559744"
---
# <a name="ca1039-lists-are-strongly-typed"></a>CA1039 : Les listes sont fortement typées
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ListsAreStronglyTyped|
|CheckId|CA1039|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Type de public ou protégé implémente <xref:System.Collections.IList?displayProperty=fullName> mais ne fournit pas de méthode fortement typée pour une ou plusieurs des opérations suivantes :

- IList.Item

- IList.Add

- IList.Contains

- IList.IndexOf

- IList.Insert

- IList.Remove

## <a name="rule-description"></a>Description de la règle
 Cette règle requiert <xref:System.Collections.IList> implémentations fournissent fortement des membres typés afin que les utilisateurs ne doivent pas effectuer un cast des arguments à la <xref:System.Object?displayProperty=fullName> tapez lorsqu’ils utilisent les fonctionnalités fournies par l’interface. Le <xref:System.Collections.IList> interface est implémentée par les collections d’objets qui sont accessibles par index. Cette règle suppose que le type qui implémente <xref:System.Collections.IList> procède ainsi pour gérer une collection d’instances d’un type plus fort que <xref:System.Object>.

 <xref:System.Collections.IList> implémente le <xref:System.Collections.ICollection?displayProperty=fullName> et <xref:System.Collections.IEnumerable?displayProperty=fullName> interfaces. Si vous implémentez <xref:System.Collections.IList>, vous devez fournir les membres fortement typés requis pour <xref:System.Collections.ICollection>. Si les objets dans la collection étendent <xref:System.ValueType?displayProperty=fullName>, vous devez fournir un membre fortement typé pour <xref:System.Collections.IEnumerable.GetEnumerator%2A> afin d’éviter la baisse de performances qui est provoquée par une opération boxing ; n’est pas requise lorsque les objets de la collection sont un type référence.

 Pour se conformer à cette règle, implémentez explicitement les membres d’interface à l’aide de noms dans le formulaire InterfaceName.InterfaceMemberName, tels que <xref:System.Collections.IList.Add%2A>. Les membres d’interface explicites utilisent les types de données qui sont déclarés par l’interface. Implémenter des membres fortement typés à l’aide du nom de membre d’interface, tel que `Add`. Déclarer des membres fortement typés comme publics et déclarez des paramètres et retourner des valeurs à être de type fort qui est géré par la collection. Les types forts remplacent les types plus faibles comme <xref:System.Object> et <xref:System.Array> qui sont déclarés par l’interface.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, implémentez explicitement <xref:System.Collections.IList> membres et fournir des alternatives fortement typés pour les membres qui ont été mentionnés précédemment. Pour le code qui implémente correctement le <xref:System.Collections.IList> interface et fournit les informations requises des membres fortement typés, consultez l’exemple suivant.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Supprimer un avertissement de cette règle lorsque vous implémentez une nouvelle collection basée sur un objet, telles qu’une liste liée, où des types qui étendent la nouvelle collection déterminent le type fort. Ces types doivent être conforme à cette règle et exposer des membres fortement typés.

## <a name="example"></a>Exemple
 Dans l’exemple suivant, le type `YourType` étend <xref:System.Collections.CollectionBase?displayProperty=fullName>, comme toutes les collections fortement typées. Notez que <xref:System.Collections.CollectionBase> fournit l’implémentation explicite de la <xref:System.Collections.IList> interface pour vous. Par conséquent, vous devez fournir uniquement des membres fortement typés pour <xref:System.Collections.IList> et <xref:System.Collections.ICollection>.

 [!code-csharp[FxCop.Design.IListStrongTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.IListStrongTypes/cs/FxCop.Design.IListStrongTypes.cs#1)]

## <a name="related-rules"></a>Règles associées
 [CA1035 : Les implémentations ICollection ont des membres fortement typés](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)

 [CA1038 : Les énumérateurs doivent être fortement typés](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

## <a name="see-also"></a>Voir aussi
 <xref:System.Collections.CollectionBase?displayProperty=fullName> <xref:System.Collections.ICollection?displayProperty=fullName>
 <xref:System.Collections.IEnumerable?displayProperty=fullName>
 <xref:System.Collections.IList?displayProperty=fullName>
 <xref:System.Object?displayProperty=fullName>
