---
title: IActiveScriptSite::GetLCID | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.GetLCID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_GetLCID
ms.assetid: 7b4a2dc1-bcf6-4bbf-884e-97b305a28eb7
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6ebcfec9764aae98f7d74ac98e0c88ecec7c4da
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992768"
---
# <a name="iactivescriptsitegetlcid"></a>IActiveScriptSite::GetLCID
Récupère l’identificateur de paramètres régionaux associé à interface utilisateur de l’ordinateur hôte. Le moteur de script utilise l’identificateur pour vous assurer que les chaînes d’erreur et d’autres éléments d’interface utilisateur générées par le moteur s’affichent dans la langue appropriée.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetLCID(  
    LCID *plcid  // address of variable for language identifier  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `plcid`  
 [out] Adresse d’une variable qui reçoit l’identificateur de paramètres régionaux pour les éléments d’interface utilisateur affichée par le moteur de script.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne une des valeurs suivantes :  
  
|Valeur de retour|Signification|  
|------------------|-------------|  
|`S_OK`|Opération réussie.|  
|`E_NOTIMPL`|Cette méthode n’est pas implémentée. Utilisez les paramètres régionaux définis par le système.|  
|`E_POINTER`|Un pointeur non valide a été spécifié.|  
  
## <a name="remarks"></a>Notes  
 Si cette méthode retourne `E_NOTIMPL`, l’identificateur de paramètres régionaux de définie par le système doit être utilisé.  
  
## <a name="see-also"></a>Voir aussi  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)