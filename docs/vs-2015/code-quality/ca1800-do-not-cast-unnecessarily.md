---
title: 'CA1800 : N’effectuez pas de cast inutilement | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1800
- DoNotCastUnnecessarily
helpviewer_keywords:
- DoNotCastUnnecessarily
- CA1800
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 49ffc66b1b7047c7b88664ac0c5198fbd51c51c6
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65682072"
---
# <a name="ca1800-do-not-cast-unnecessarily"></a>CA1800 : N'effectuez pas de cast inutilement
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotCastUnnecessarily|
|CheckId|CA1800|
|Category|Microsoft.Performance|
|Modification avec rupture|Sans rupture|

## <a name="cause"></a>Cause
 Une méthode effectue des casts en double sur un de ses arguments ou les variables locales. Pour l’analyse complète par cette règle, l’assembly testé doit être construit à l’aide des informations de débogage et le fichier de base de données (.pdb) du programme associé doit être disponible.

## <a name="rule-description"></a>Description de la règle
 Les casts en doublon font baisser les performances, surtout lorsque les casts sont exécutés au sein d'instructions d'itération compactes. Pour les opérations de casts en doublon explicites, stocker le résultat du cast dans une variable locale et utilisez la variable locale au lieu des opérations de cast en double.

 Si C# `is` opérateur est utilisé pour déterminer si le cast va réussir avant l’exécution proprement dite, envisagez de tester le résultat de la `as` opérateur à la place. Cela fournit les mêmes fonctionnalités sans l’opération de cast implicite est effectuée par le `is` opérateur.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, modifiez l’implémentation de méthode pour réduire le nombre d’opérations de cast.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est recommandé de supprimer un avertissement de cette règle, ou à ignorer la règle, si les performances ne sont pas un problème.

## <a name="example"></a>Exemple
 L’exemple suivant montre une méthode qui viole la règle à l’aide de C# `is` opérateur. Une deuxième méthode satisfait la règle en remplaçant le `is` opérateur avec un test par rapport au résultat de la `as` opérateur, ce qui réduit le nombre d’opérations de cast par itération de deux à un.

 [!code-csharp[FxCop.Performance.UnnecessaryCastsAsIs#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCastsAsIs/cs/FxCop.Performance.UnnecessaryCastsAsIs.cs#1)]

## <a name="example"></a>Exemple
 L’exemple suivant montre une méthode, `start_Click`, qui a plusieurs conversions explicites en double, ce qui viole la règle et une méthode, `reset_Click`, ce qui satisfait la règle en stockant le cast dans une variable locale.

 [!code-csharp[FxCop.Performance.UnnecessaryCasts#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCasts/cs/FxCop.Performance.UnnecessaryCasts.cs#1)]
 [!code-vb[FxCop.Performance.UnnecessaryCasts#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCasts/vb/FxCop.Performance.UnnecessaryCasts.vb#1)]

## <a name="see-also"></a>Voir aussi
 [as](https://msdn.microsoft.com/library/a9be126b-cbf4-4990-a70d-d0e1983cad0e) [is](https://msdn.microsoft.com/library/bc62316a-d41f-4f90-8300-c6f4f0556e43)
