---
title: 'Procédure : Utiliser l’outil recherche | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Window Finder Tool
ms.assetid: 5841926b-08c3-4e43-88bd-4223d04f9aef
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 00535fd336f504afcebdd24a4d009a10f7f6ff33
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440302"
---
# <a name="how-to-use-the-finder-tool"></a>Procédure : Utiliser l’outil de recherche
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez utiliser l’outil de recherche dans les **rechercher une fenêtre** boîte de dialogue pour afficher la fenêtre Propriétés ou des messages. L’outil recherche peut également rechercher des fenêtres enfants désactivées et discerner fenêtre pour mettre en surbrillance si désactivées fenêtres enfants se chevauchent.  
  
 ![Spy&#43; &#43; boîte de dialogue de fenêtre Rechercher](../debugger/media/icon-spy-find.png "Icon_Spy ++ _Find")  
Outil de recherche dans la boîte de dialogue Rechercher une fenêtre  
  
 La figure ci-dessus illustre la boîte de dialogue Rechercher une fenêtre après l’étape 3 ci-dessous.  
  
### <a name="to-display-window-properties-or-messages"></a>Pour afficher la fenêtre Propriétés ou messages  
  
1. Réorganisez vos fenêtres afin que Spy ++ et la fenêtre cible sont visibles.  
  
2. À partir de la **Spy** menu, choisissez **rechercher une fenêtre**.  
  
     Le [boîte de dialogue Rechercher une fenêtre](../debugger/find-window-dialog-box.md) s’ouvre.  
  
3. Faites glisser le **outil recherche** sur la fenêtre cible.  
  
     Lorsque vous faites glisser l’outil, le **rechercher une fenêtre** boîte de dialogue affiche des détails sur la fenêtre sélectionnée.  
  
     – ou –  
  
     Si vous avez le handle de la fenêtre que vous souhaitez examiner (par exemple, copié à partir du débogueur), tapez-le dans la **gérer** zone de texte.  
  
    > [!TIP]
    > Pour réduire l’encombrement de l’écran, sélectionnez le **Masquer Spy ++** option. Cette option masque la fenêtre Spy ++ principale, ce qui laisse uniquement le **rechercher une fenêtre** boîte de dialogue visible en haut de vos autres applications. La fenêtre principale de Spy ++ est restaurée lorsque vous cliquez sur **OK** ou **Annuler**, ou lorsque vous supprimez le **Masquer Spy ++** option.  
  
4. Sous **afficher**, sélectionnez **propriétés** ou **Messages**.  
  
5. Cliquez sur **OK**.  
  
     Si vous avez sélectionné **propriétés**, le [boîte de dialogue Propriétés de fenêtre](../debugger/window-properties-dialog-box.md) s’ouvre. Si vous avez sélectionné **Messages**, un [vue Messages](../debugger/messages-view.md) fenêtre s’ouvre.  
  
## <a name="see-also"></a>Voir aussi  
 [Vues Spy++](../debugger/spy-increment-views.md)   
 [Utilisation de Spy++](../debugger/using-spy-increment.md)   
 [Informations de référence sur Spy++](../debugger/spy-increment-reference.md)
