---
title: DebugBreak et __debugbreak | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- DebugBreak
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], DebugBreak function
- DebugBreak function
- breakpoints, DebugBreak function
ms.assetid: 9787c795-df94-4f48-bc8d-3bf899b67421
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ea2a40943233e7dfffd3340f2e27da1d43a76a0a
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65691176"
---
# <a name="debugbreak-and-debugbreak"></a>DebugBreak et __debugbreak
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez appeler la fonction Win32 DebugBreak ou l’objet intrinsèque [__debugbreak](https://msdn.microsoft.com/library/1d1e1c0c-891a-4613-ae4b-d790094ba830) à n’importe quel endroit de votre code. `DebugBreak` et `__debugbreak` reviennent à définir un point d'arrêt à cet emplacement.  
  
 Étant donné que `DebugBreak` est un appel à une fonction système, les symboles de débogage de système doivent être installés pour vérifier que les informations de pile des appels correctes sont affichées après l’arrêt. À défaut, les informations de la pile des appels affichées par le débogueur peuvent être décalées d'un frame. Si vous utilisez `__debugbreak`, les symboles ne sont pas requis.  
  
## <a name="see-also"></a>Voir aussi  
 [Compilateur, fonctions intrinsèques](https://msdn.microsoft.com/library/48bb9929-7d78-4fd8-a092-ae3c9f971858)   
 [Sécurité du débogueur](../debugger/debugger-security.md)   
 [Débogage du code natif](../debugger/debugging-native-code.md)   
 [Spécifier les fichiers de symbole (.pdb) et les fichiers sources](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
