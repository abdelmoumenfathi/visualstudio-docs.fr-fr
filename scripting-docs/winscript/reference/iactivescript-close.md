---
title: IActiveScript::Close | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.Close
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_Close
ms.assetid: cc7dd63b-1d7e-410a-857b-09ea3aade275
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53b71471ada55751de301391fdcc70387c1bb6c2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935677"
---
# <a name="iactivescriptclose"></a>IActiveScript::Close
Provoque le moteur de script abandonner n’importe quel script actuellement chargé, son état est perdu et libérer les pointeurs d’interface qu’à d’autres objets, donc dans un état fermé. Récepteurs d’événements, le texte de script exécuté immédiatement et appels de macro qui sont déjà en cours d’exécution sont terminés avant les modifications d’état (utilisez [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) d’annuler un thread de script en cours d’exécution). Cette méthode doit être appelée par l’hôte de création avant de l’interface est libéré pour éviter les problèmes de référence circulaire.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Close(void);  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne une des valeurs suivantes :  
  
|Value|Signification|  
|-----------|-------------|  
|`S_OK`|Opération réussie.|  
|`E_UNEXPECTED`|L’appel n’était pas attendu (par exemple, le moteur de script était déjà dans l’état fermé).|  
|`OLESCRIPT_S_PENDING`|La méthode a été en file d’attente avec succès, mais l’état n’a pas encore changé. Quand les modifications d’état, le site doit être rappelé sur le [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) (méthode).|  
|`S_FALSE`|La méthode a réussi, mais le script a déjà été fermé.|  
  
## <a name="see-also"></a>Voir aussi  
 [IActiveScript](../../winscript/reference/iactivescript.md)