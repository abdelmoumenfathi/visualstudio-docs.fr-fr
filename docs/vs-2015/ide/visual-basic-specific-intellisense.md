---
title: Options IntelliSense spécifiques à Visual Basic | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
ms.assetid: 4dec8753-05e5-4f74-b304-5f8c4ed8723b
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f471ed62a3bb53c4779c0b2d80315f10bfc85993
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65696480"
---
# <a name="visual-basic-specific-intellisense"></a>Options IntelliSense spécifiques à Visual Basic
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

L’éditeur de code source de Visual Basic propose les fonctionnalités IntelliSense suivantes :  
  
- Conseils de syntaxe  
  
     Les conseils syntaxiques affichent la syntaxe de l’instruction que vous tapez. Cela est utile pour les instructions telles que [Declare](https://msdn.microsoft.com/library/d3f21fb0-b804-4c99-97ed-583b23894cf1).  
  
## <a name="automatic-completion"></a>Saisie semi-automatique  
  
- Saisie semi-automatique de divers mots clés  
  
   Par exemple, si vous tapez `goto` suivi d’un espace, IntelliSense affiche une liste des étiquettes définies dans un menu déroulant. Les autres mots clés pris en charge sont `Exit`, `Implements`, `Option` et `Declare`.  
  
- Saisie semi-automatique pour `Enum` et`Boolean`  
  
   Quand une instruction fait référence à un membre d’une énumération, IntelliSense affiche la liste des membres d’`Enum`. Quand une instruction fait référence à un `Boolean`, IntelliSense affiche un menu déroulant contenant les valeurs True et False.  
  
  Pour désactiver par défaut la saisie semi-automatique, désélectionnez l’option **Répertorier automatiquement les membres** dans la page de propriétés **Général** du dossier **Visual Basic**.  
  
  Vous pouvez appeler manuellement la saisie semi-automatique en appelant les fonctionnalités Liste des membres, Compléter le mot ou ALT+FLÈCHE DROITE. Pour plus d’informations, consultez [Utilisation d’IntelliSense](../ide/using-intellisense.md).  
  
## <a name="intellisense-in-zone"></a>IntelliSense par zone  
 IntelliSense par zone aide les développeurs Visual Basic qui doivent déployer leurs applications via [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] et sont contraints à des paramètres de confiance partielle. Cette fonctionnalité :  
  
- vous permet de choisir les autorisations avec lesquelles l’application s’exécutera ;  
  
- affiche les API dans la Zone choisie comme disponibles dans la Liste des membres, et les API nécessitant des autorisations supplémentaires comme non disponibles.  
  
  Pour plus d’informations, consultez [Sécurité d’accès du code pour les applications ClickOnce](../deployment/code-access-security-for-clickonce-applications.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de la fonctionnalité IntelliSense](../ide/using-intellisense.md)
