---
title: "'default' ne peut apparaître qu’une seule fois dans une instruction 'switch' | Microsoft Docs"
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1027
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a94100f4-6ee5-4759-b635-9d309e47111e
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 24162efcc720d9c0073f8a5799c6278b8d3c8c62
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946353"
---
# <a name="default-can-only-appear-once-in-a-switch-statement"></a>'default' ne peut apparaître qu'une fois dans une instruction 'switch'
Vous avez tenté d’utiliser le **par défaut** instruction plusieurs fois dans une instruction switch. Le cas par défaut est toujours la dernière instruction case dans une instruction switch (c’est le cas de passage).  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
- Supprimez les supplémentaire **par défaut** cas les instructions à partir de votre `switch` instruction (utilisez à la plupart des instruction case par défaut dans votre instruction switch).  
  
## <a name="see-also"></a>Voir aussi  
 [Instruction switch](../../javascript/reference/switch-statement-javascript.md)   
 [Contrôle du flux de programme](../../javascript/controlling-program-flow-javascript.md)   
 [Mots réservés JavaScript](../../javascript/reference/javascript-reserved-words.md)