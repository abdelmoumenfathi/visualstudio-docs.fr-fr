---
title: 'CA1724 : Les noms de types ne doivent pas être identiques aux espaces de noms'
ms.date: 09/28/2018
ms.topic: reference
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f81327324de937df57edfb36cae34d613f6298a5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546018"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724 : Noms de types ne doivent pas correspondre aux espaces de noms

|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|Category|Microsoft.Naming|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause

Un nom de type correspond à un nom d’espace de noms référencé qui a un ou plusieurs types visibles de l’extérieur. La comparaison des noms respecte la casse.

## <a name="rule-description"></a>Description de la règle

Les noms de type créés par l’utilisateur ne doivent pas correspondre les noms des espaces de noms référencés qui ont des types visibles de l’extérieur. Violation de cette règle peut réduire la facilité d’utilisation de votre bibliothèque.

## <a name="how-to-fix-violations"></a>Comment corriger les violations

Renommer le type de sorte qu’il ne correspond pas à celui d’un espace de noms référencé qui a des types visibles de l’extérieur.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements

Pour un nouveau développement, aucun connus scénarios se produisent où vous devez supprimer un avertissement de cette règle. Avant de pouvoir supprimer l’avertissement, étudiez attentivement la façon dont les utilisateurs de votre bibliothèque peuvent être désorientés par le nom correspondant. Pour livrer des bibliothèques, vous devrez peut-être supprimer un avertissement de cette règle.