---
title: IEnumDebugReferenceInfo2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugReferenceInfo2
helpviewer_keywords:
- IEnumDebugReferenceInfo2
ms.assetid: 7ed01441-686f-4032-8268-a4c750f19f85
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 21c39c553a153707bad707d50cf5a13ae87973fd
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58953162"
---
# <a name="ienumdebugreferenceinfo2"></a>IEnumDebugReferenceInfo2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Cette interface énumère [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) structures.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugReferenceInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs  
 Le moteur de débogage (dé) implémente cette interface dans le cadre de sa prise en charge pour les références aux objets en mémoire. Cette interface doit être implémentée uniquement si les références sont prises en charge.  
  
## <a name="notes-for-callers"></a>Notes de publication pour les appelants  
 Les appels de Visual Studio [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) pour obtenir cette interface.  
  
## <a name="methods-in-vtable-order"></a>Méthodes dans l'ordre Vtable  
 Le tableau suivant présente les méthodes de `IEnumDebugReferenceInfo2`.  
  
|Méthode|Description|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-next.md)|Récupère un nombre spécifié de [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) structures dans une séquence d’énumération.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-skip.md)|Ignore un nombre spécifié de [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) structures dans la séquence d’énumération.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-reset.md)|Réinitialise une séquence d’énumération au début.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-clone.md)|Crée un énumérateur qui contient le même état d’énumération que l’énumérateur en cours.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-getcount.md)|Obtient le nombre de [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) structures dans un énumérateur.|  
  
## <a name="remarks"></a>Notes  
 Une référence est essentiellement un type et une adresse, tandis qu’une propriété est un nom, le type et l’adresse. Une référence persiste tant que l’objet référencé existe dans la mémoire. Consultez [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) pour plus d’informations.  
  
## <a name="requirements"></a>Configuration requise  
 En-tête : msdbg.h  
  
 Espace de noms : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces principales](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)
