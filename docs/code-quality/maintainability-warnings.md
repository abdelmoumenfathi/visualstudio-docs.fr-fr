---
title: avertissements liés à la facilité de maintenance
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 752a637ef01c33aa4e93083e9578d01f00977960
ms.sourcegitcommit: 92a04c57ac0a49f304fa2ea5043436f30068c3cd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/21/2019
ms.locfileid: "65976164"
---
# <a name="maintainability-warnings"></a>Avertissements liés à la maintenabilité

Avertissements de la facilité de gestion prennent en charge la gestion des bibliothèques et des applications.

## <a name="in-this-section"></a>Dans cette section

| Règle | Description |
|-----------|-----------------------------------|
| [CA1500 : Les noms de variables ne doivent pas correspondre aux noms de champs](../code-quality/ca1500-variable-names-should-not-match-field-names.md) | Une méthode d’instance déclare un paramètre ou une variable locale dont le nom correspond à un champ d’instance du type déclarant, ce qui entraîne des erreurs. |
| [CA1501 : Éviter l’excès d’héritage](../code-quality/ca1501-avoid-excessive-inheritance.md) | Un type est imbriqué de plus de quatre niveaux dans sa hiérarchie d'héritage. Les hiérarchies de type profondément imbriquées peuvent être difficiles à suivre, comprendre et gérer. |
| [CA1502 : Éviter l’excès de complexité](../code-quality/ca1502-avoid-excessive-complexity.md) | Cette règle évalue le nombre de chemins linéairement indépendants dans la méthode, déterminé par le nombre et la complexité des branches conditionnelles. |
| [CA1504 : Passez en revue les noms de champs trompeurs](../code-quality/ca1504-review-misleading-field-names.md) | Le nom d’un champ d’instance commence par « s_ » ou le nom de statique (partagé dans [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) champ commence par « m_ ». |
| [CA1505 : Éviter le code](../code-quality/ca1505-avoid-unmaintainable-code.md) | Un type ou une méthode a une faible valeur d'indice de maintenabilité. Un faible indice de maintenabilité indique qu'un type ou qu'une méthode est probablement difficile à maintenir et qu'il/elle se prête bien à une nouvelle conception. |
| [CA1506 : Éviter les couplages de classe excessifs](../code-quality/ca1506-avoid-excessive-class-coupling.md) | Cette règle mesure l'accouplement de classes en comptant le nombre de références de type uniques contenues dans un type ou une méthode. |
| [CA1507 : Utilisez nameof à la place de chaîne](../code-quality/ca1507.md) | Un littéral de chaîne est utilisé en tant qu’argument dans lequel un `nameof` expression peut être utilisée. |

## <a name="see-also"></a>Voir aussi

- [Mesurer la complexité et la maintenabilité du Code managé](../code-quality/code-metrics-values.md)