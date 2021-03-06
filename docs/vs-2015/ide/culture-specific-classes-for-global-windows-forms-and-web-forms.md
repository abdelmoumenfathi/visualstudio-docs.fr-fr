---
title: Classes spécifiques à la culture pour les Windows Forms et les Web Forms globaux | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- globalization [Windows Forms], classes
- Web applications [.NET Framework], globalization
- culture, culture-specific classes
- numbers, international
- localization [Windows Forms], classes
- globalization [Visual Studio], culture-specific classes
- Windows Forms, localization
- international applications [Visual Studio], data formats
- time [Visual Studio], international
- dates [Visual Studio], international
- culture
- international characters
- currency formats
- ASP.NET, globalization
- classes [Visual Studio], culture-specific
- localization [Visual Studio], culture-specific classes
ms.assetid: 0d06a0a4-f887-4f7c-bde7-1d543c06f803
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e18cda54431eec580464ccb59c5c6b6cce87d225
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65701117"
---
# <a name="culture-specific-classes-for-global-windows-forms-and-web-forms"></a>Classes spécifiques à la culture pour les Windows Forms et les Web Forms globaux
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Chaque culture a ses propres conventions d’affichage des dates, des heures, des nombres, des devises et d’autres informations. L’espace de noms <xref:System.Globalization> contient des classes qui peuvent être utilisées pour modifier la façon dont les valeurs spécifiques à une culture sont affichées, comme <xref:System.Globalization.DateTimeFormatInfo>, **Calendar** et <xref:System.Globalization.NumberFormatInfo>.  
  
## <a name="using-the-culture-setting"></a>Utilisation du paramètre de culture  
 Mais la plupart du temps, vous utilisez le paramètre de culture stocké dans l’application ou dans le panneau de configuration **Options régionales** pour déterminer automatiquement les conventions au moment de l’exécution et mettre en forme les informations en conséquence. Pour plus d’informations sur la définition de la culture, consultez [Guide pratique pour Définir la Culture et la Culture d’interface utilisateur pour la globalisation des Windows Forms](https://msdn.microsoft.com/694e049f-0b91-474a-9789-d35124f248f0) ou [Comment : Définir la Culture et la Culture d’interface utilisateur pour la globalisation des pages Web ASP.NET](https://msdn.microsoft.com/library/76091f86-f967-4687-a40f-de87bd8cc9a0). Les classes qui mettent en forme automatiquement les informations en fonction du paramètre de culture sont appelées des classes spécifiques à une culture. <xref:System.IFormattable.ToString%2A?displayProperty=fullName>, <xref:System.Console.WriteLine%2A?displayProperty=fullName> et <xref:System.String.Format%2A?displayProperty=fullName> sont des méthodes spécifiques à une culture. `MonthName` et `WeekDayName` sont des méthodes spécifiques à une culture (dans le langage Visual Basic).  
  
 Par exemple, le code suivant montre comment vous pouvez utiliser la méthode <xref:System.IFormattable.ToString%2A> pour mettre en forme la devise pour la culture active :  
  
```vb  
' Put the Imports statements at the beginning of the code module  
Imports System.Threading  
Imports System.Globalization  
' Display a number with the culture-specific currency formatting  
Dim MyInt As Integer = 100  
Console.WriteLine(MyInt.ToString("C", Thread.CurrentThread.CurrentCulture))  
  
```  
  
```csharp  
// Put the using statements at the beginning of the code module  
using System.Threading;  
using System.Globalization;  
// Display a number with the culture-specific currency formatting  
int myInt = 100;  
Console.WriteLine(myInt.ToString("C", Thread.CurrentThread.CurrentCulture));  
```  
  
 Si la culture est définie sur « fr-FR », vous voyez ceci dans la fenêtre de sortie :  
  
 `100,00`  
  
 Si la culture est définie sur « en-US », vous voyez ceci dans la fenêtre de sortie :  
  
 `$100.00`  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.IFormattable.ToString%2A?displayProperty=fullName>   
 <xref:System.Globalization.DateTimeFormatInfo>   
 <xref:System.Globalization.NumberFormatInfo>   
 <xref:System.Globalization.Calendar>   
 <xref:System.Console.WriteLine%2A?displayProperty=fullName>   
 <xref:System.String.Format%2A?displayProperty=fullName>   
 [Globalisation et localisation d’applications](../ide/globalizing-and-localizing-applications.md)
