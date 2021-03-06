---
title: IDebugApplication::FireDebuggerEvent | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.FireDebuggerEvent
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::FireDebuggerEvent
ms.assetid: fd1f602e-fc15-4158-a6e7-497ff5b4a509
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ad865f05cc70f462d65d6fbead4143b82a9fa489
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62990915"
---
# <a name="idebugapplicationfiredebuggerevent"></a>IDebugApplication::FireDebuggerEvent
Déclenche un événement générique pour le débogueur `IApplicationDebugger` interface.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT FireDebuggerEvent(  
   REFGUID    riid,  
   IUnknown*  punk  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `riid`  
 [in] Un GUID pour l’objet.  
  
 `punk`  
 [in] Un objet d’événement à passer au débogueur.  
  
## <a name="return-value"></a>Valeur de retour  
 La méthode retourne `HRESULT`. Les valeurs possibles sont notamment celles figurant dans le tableau suivant.  
  
|Value|Description|  
|-----------|-----------------|  
|`S_OK`|La méthode a réussi.|  
|`E_NOTIMPL`|La méthode n’est pas implémentée actuellement.|  
  
## <a name="remarks"></a>Notes  
 La sémantique du GUID et le `IUnknown` sont entièrement définie par le débogueur/application.  
  
 Cette méthode permet à des extensions personnalisées du modèle débogueur ; Il n’est pas implémentée actuellement.  
  
 Cette méthode provoque `IApplicationDebugger::onDebuggerEvent` à appeler.  
  
## <a name="see-also"></a>Voir aussi  
 [Interface IDebugApplication](../../winscript/reference/idebugapplication-interface.md)   
 [IApplicationDebugger::onDebuggerEvent](../../winscript/reference/iapplicationdebugger-ondebuggerevent.md)