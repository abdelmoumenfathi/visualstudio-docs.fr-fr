---
title: 'CA1809 : Évitez le surplus de variables locales'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1809
- AvoidExcessiveLocals
helpviewer_keywords:
- AvoidExcessiveLocals
- CA1809
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f4ac6947f8424c3b9aa7429ee378b4bb89be73ca
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545239"
---
# <a name="ca1809-avoid-excessive-locals"></a>CA1809 : Évitez le surplus de variables locales

|||
|-|-|
|TypeName|AvoidExcessiveLocals|
|CheckId|CA1809|
|Category|Microsoft.Performance|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Un membre contient plus de 64 variables locales, certains d'entre eux peuvent être généré par le compilateur.

## <a name="rule-description"></a>Description de la règle
 Une optimisation des performances courante consiste à stocker une valeur dans un Registre de processeur au lieu d’en mémoire, ce qui est appelé *enregistrement* la valeur. Le common language runtime considère que jusqu'à 64 variables locales pour l’enregistrement. Les variables qui ne sont pas enregistrées sont placées sur la pile et doivent être déplacés vers un Registre avant toute manipulation. Pour permettre le risque que toutes les variables locales obtenir inscrites dans le Registre, limiter le nombre de variables locales à 64.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, refactorisez l’implémentation pour utiliser pas plus de 64 variables locales.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est recommandé de supprimer un avertissement de cette règle, ou pour désactiver la règle, si les performances ne sont pas un problème.

## <a name="related-rules"></a>Règles associées
 [CA1804 : Supprimez les variables locales inutilisées](../code-quality/ca1804-remove-unused-locals.md)