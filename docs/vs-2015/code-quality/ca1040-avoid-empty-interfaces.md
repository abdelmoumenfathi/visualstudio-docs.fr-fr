---
title: 'CA1040 : Éviter les interfaces vides | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: bc785967b4e27599b4a04aeb7740b53b5076938d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62559741"
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040 : Éviter les interfaces vides
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidEmptyInterfaces|
|CheckId|CA1040|
|Category|Microsoft.Design|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 L’interface ne déclare aucun membre ni implémenter deux ou plusieurs autres interfaces.

## <a name="rule-description"></a>Description de la règle
 Les interfaces définissent des membres qui fournissent un comportement ou un contrat d'utilisation. Les fonctionnalités décrites par l'interface peuvent être adoptées par tout type, indépendamment de l'endroit où le type figure dans la hiérarchie d'héritage. Un type implémente une interface en fournissant des implémentations pour les membres de celle-ci. Une interface vide ne définit pas de membres. Par conséquent, il ne définit pas un contrat qui peut être implémenté.

 Si votre conception inclut vide interfaces que les types sont censés implémenter, vous utilisez probablement une interface en tant qu’un marqueur ou un moyen d’identifier un groupe de types. Si cette identification se produit au moment de l’exécution, la méthode correcte pour ce faire consiste à utiliser un attribut personnalisé. Utilisez la présence ou l’absence de l’attribut, ou les propriétés de l’attribut, pour identifier les types de cibles. Si l’identification doit avoir lieu au moment de la compilation, il est acceptable d’utiliser une interface vide.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Supprimer l’interface ou ajouter des membres. Si l’interface vide est utilisé pour étiqueter un ensemble de types, remplacez l’interface avec un attribut personnalisé.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Il est possible de supprimer un avertissement de cette règle lorsque l’interface est utilisée pour identifier un ensemble de types au moment de la compilation.

## <a name="example"></a>Exemple
 L’exemple suivant montre une interface vide.

 [!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.InterfacesNotEmpty/cpp/FxCop.Design.InterfacesNotEmpty.cpp#1)]
 [!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.InterfacesNotEmpty/cs/FxCop.Design.InterfacesNotEmpty.cs#1)]
 [!code-vb[FxCop.Design.InterfacesNotEmpty#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.InterfacesNotEmpty/vb/FxCop.Design.InterfacesNotEmpty.vb#1)]
