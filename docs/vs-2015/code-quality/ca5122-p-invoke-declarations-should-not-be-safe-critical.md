---
title: 'Déclarations ca5122 : P-Invoke ne doivent pas être sécurisées critiques | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: f2581a6d-2a0e-40c1-b600-f5dc70909200
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: eff316ac6f5d73e157e3dbef5126195bd0d62878
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58951763"
---
# <a name="ca5122-pinvoke-declarations-should-not-be-safe-critical"></a>CA5122 : les déclarations P/Invoke ne doivent pas être sécurisées
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|PInvokesShouldNotBeSafeCriticalFxCopRule|
|CheckId|CA5122|
|Category|Microsoft.Security|
|Modification avec rupture|Rupture|

## <a name="cause"></a>Cause
 Une déclaration P/Invoke a été marquée avec <xref:System.Security.SecuritySafeCriticalAttribute>:

```csharp
[assembly: AllowPartiallyTrustedCallers]

// ...
public class C
{
    [SecuritySafeCritical]
    [DllImport("kernel32.dll")]
    public static extern bool Beep(int frequency, int duration); // CA5122 – safe critical p/invoke
   }
```

 Dans cet exemple, `C.Beep(...)` a été marqué comme méthode critique sécurisée.

## <a name="rule-description"></a>Description de la règle
 Les méthodes sont marquées SecuritySafeCritical lorsqu’elles effectuent une opération relative à la sécurité, mais elle peuvent également être utilisées en toute sécurité par du code transparent. L'une des règles fondamentales de la transparence de la sécurité est que le code transparent peut ne jamais appeler directement le code natif via un P/Invoke. Par conséquent, marquer une méthode P/Invoke comme critique sécurisé ne permet pas au code transparent de l’appeler et s’avère trompeur pour l’analyse de sécurité.

## <a name="how-to-fix-violations"></a>Comment corriger les violations
 Pour rendre un P/Invoke accessible au code transparent, vous devez lui exposer une méthode de wrapper critique sécurisée :

```csharp
[assembly: AllowPartiallyTrustedCallers

class C
{
   [SecurityCritical]
   [DllImport(“kernel32.dll”, EntryPoint=”Beep”)]
   private static extern bool BeepPinvoke(int frequency, int duration); // Security Critical P/Invoke

   [SecuritySafeCritical]
   public static bool Beep(int frequency, int duration)
   {
      return BeepPInvoke(frequency, duration);
   }
}
```

## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements
 Ne supprimez aucun avertissement de cette règle.
