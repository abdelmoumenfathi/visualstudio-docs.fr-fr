---
title: Exceptions (Kit de développement logiciel Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], exception handling
ms.assetid: 7279dc16-db14-482c-86b8-7b3da5a581d2
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e42e4dbe18b0d2fe6da522d24d493270518e884e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47508829"
---
# <a name="exception-handling-visual-studio-sdk"></a>Gestion des exceptions (SDK Visual Studio)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [(SDK Visual Studio) de gestion des exceptions](https://docs.microsoft.com/visualstudio/extensibility/debugger/exception-handling-visual-studio-sdk).  
  
La section suivante décrit le processus qui se produit lorsque des exceptions sont levées.  
  
## <a name="exception-handling-process"></a>Processus de gestion d’exception  
  
1.  Quand une exception est levée d’abord, mais avant qu’il est géré par le Gestionnaire d’exceptions dans le programme en cours de débogage, le moteur de débogage (dé) envoie une [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) avec le Gestionnaire de débogage de session (SDM) comme un événement d’arrêt. Le `IDebugExceptionEvent2` est envoyé si seuls les paramètres d’exception (spécifiée dans la boîte de dialogue Exceptions dans le package de débogage) indiquent que l’utilisateur souhaite arrêter sur les notifications des exceptions de première chance.  
  
2.  Les appels SDM [IDebugExceptionEvent2::GetException](../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) pour obtenir la propriété d’exception.  
  
3.  Les appels de package de débogage [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) pour déterminer quelles options de présenter à l’utilisateur.  
  
4.  Le package de débogage demande à l’utilisateur comment gérer l’exception en ouvrant une boîte de dialogue Exceptions de première chance.  
  
5.  Si l’utilisateur choisit de continuer, le SDM appelle [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md).  
  
    -   Si la méthode retourne S_OK, appelle [IDebugExceptionEvent2::PassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md).  
  
         - ou -  
  
         Si la méthode retourne S_FALSE, le programme en cours de débogage est donné à une seconde chance pour gérer l’exception.  
  
6.  Si le programme en cours de débogage n’a aucun gestionnaire pour une exception de seconde chance, l’Allemagne envoie un `IDebugExceptionEvent2` pour le SDM comme **EVENT_SYNC_STOP**.  
  
7.  Le package de débogage demande à l’utilisateur comment gérer l’exception en ouvrant une boîte de dialogue Exceptions de première chance.  
  
8.  Les appels de package de débogage [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) pour déterminer quelles options de présenter à l’utilisateur.  
  
9. Le package de débogage demande à l’utilisateur comment gérer l’exception en ouvrant une boîte de dialogue d’exception de seconde chance.  
  
10. Si la méthode retourne S_OK, appelle `IDebugExceptionEvent2::PassToDebuggee`.  
  
## <a name="see-also"></a>Voir aussi  
 [Événements d’appel du débogueur](../../extensibility/debugger/calling-debugger-events.md)
