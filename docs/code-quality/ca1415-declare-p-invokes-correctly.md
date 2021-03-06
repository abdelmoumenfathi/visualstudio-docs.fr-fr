---
title: 'CA1415 : Déclarer correctement les méthodes P-Invoke'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da6448a414437a07b545a999b35031f82e9a8689
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546184"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415 : Déclarer correctement les méthodes P/Invoke

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|Category|Microsoft.Interoperability|
|Modification avec rupture|Sans rupture - Si P/Invoke qui déclare le paramètre ne peut pas être visible à l’extérieur de l’assembly. Avec rupture - Si P/Invoke qui déclare le paramètre peut être consulté en dehors de l’assembly.|

## <a name="cause"></a>Cause
 Une méthode non managé est déclarée de manière incorrecte.

## <a name="rule-description"></a>Description de la règle
 Une plateforme d’appeler la méthode accède à un code non managé et est définie à l’aide de la `Declare` mot clé dans [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ou <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. Actuellement, cette règle recherche des déclarations de méthode qui ciblent des fonctions Win32 présentant un pointeur vers un paramètre de structure OVERLAPPED non managé et le paramètre managé correspondant n’est pas un pointeur vers un <xref:System.Threading.NativeOverlapped?displayProperty=fullName> structure.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour corriger une violation de cette règle, déclarez correctement la plateforme appeler la méthode.

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.

## <a name="example"></a>Exemple
 L’exemple suivant illustre les méthodes qui violent la règle et satisfaire à la règle non managé.

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]

## <a name="see-also"></a>Voir aussi
 [Interopération avec du code non managé](/dotnet/framework/interop/index)