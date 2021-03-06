---
title: ISimpleConnectionPoint::DescribeEvents | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISimpleConnectionPoint.DescribeEvents
apilocation:
- pdm.dll
helpviewer_keywords:
- ISimpleConnectionPoint::DescribeEvents
ms.assetid: 659ea05f-d41e-424a-bb38-df7672b2d135
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b5824f945ad25f177fc169b58157377bf53bcce
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62786417"
---
# <a name="isimpleconnectionpointdescribeevents"></a>ISimpleConnectionPoint::DescribeEvents
Retourne le DISPID pour chaque événement dans une plage spécifiée d’événements.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT DescribeEvents(  
   ULONG    iEvent,  
   ULONG    cEvents,  
   DISPID*  prgid,  
   BSTR*    prgbstr,  
   ULONG*   pcEventsFetched  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `iEvent`  
 [in] Index du premier événement à récupérer.  
  
 `cEvents`  
 [in] Nombre d’événements à récupérer.  
  
 `prgid`  
 [out] Tableau de DISPID des valeurs d’événement.  
  
 `prgbstr`  
 [out] Tableau des noms d’événement.  
  
 `pcEventsFetched`  
 [out] Le nombre réel d’événements extraites.  
  
## <a name="return-value"></a>Valeur de retour  
 La méthode retourne `HRESULT`. Les valeurs possibles sont notamment celles figurant dans le tableau suivant.  
  
|Value|Description|  
|-----------|-----------------|  
|`S_OK`|La méthode a réussi.|  
|`S_FALSE`|Plusieurs événements ont été demandées qu’étaient disponibles. Événements indisponibles sont représentés par DISPID_NULL et un BSTR null.|  
|`E_INVALIDARG`|Aucun élément ne peut être extraite.|  
  
## <a name="remarks"></a>Notes  
 Cette méthode retourne le DISPID et le nom de chaque événement dans une plage spécifiée d’événements.  
  
## <a name="see-also"></a>Voir aussi  
 [Interface ISimpleConnectionPoint](../../winscript/reference/isimpleconnectionpoint-interface.md)