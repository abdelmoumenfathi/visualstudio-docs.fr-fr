---
title: IDebugReference2::GetReferenceInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::GetReferenceInfo
helpviewer_keywords:
- IDebugReference2::GetReferenceInfo
ms.assetid: ae611714-f114-4cf2-b5bb-37461e6ff289
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 400fe23ae80ad1e0f00e8571e96471fa267a5efc
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211908"
---
# <a name="idebugreference2getreferenceinfo"></a>IDebugReference2::GetReferenceInfo
Obtient le [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) structure qui décrit une référence. Réservé à un usage ultérieur.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetReferenceInfo ( 
   DEBUGREF_INFO_FLAGS   dwFields,
   DWORD                 nRadix,
   DWORD                 dwTimeout,
   IDebugReference2**    rgpArgs,
   DWORD                 dwArgCount,
   DEBUG_REFERENCE_INFO* pReferenceInfo
);
```

```csharp
int GetReferenceInfo ( 
   enum_DEBUGREF_INFO_FLAGS  dwFields,
   uint                      nRadix,
   uint                      dwTimeout,
   IDebugReference2[]        rgpArgs,
   uint                      dwArgCount,
   DEBUG_REFERENCE_INFO[]    pReferenceInfo
);
```

## <a name="parameters"></a>Paramètres
`dwFields`\
[in] Une combinaison d’indicateurs de la [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md) énumération qui déterminent les champs à compléter le [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) structure.

`nRadix`\
[in] La base à utiliser dans toutes les informations numériques de mise en forme.

`dwTimeout`\
[in] Durée maximale, en millisecondes, à attendre avant de retourner à partir de cette méthode. Utilisez `INFINITE` pour attendre indéfiniment.

`rgpArgs`\
[in] Un tableau de [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objets. Réservé pour une utilisation ultérieure ; la valeur est une valeur null.

`dwArgCount`\
[in] Le nombre d’arguments de référence dans le `rgpArgs` tableau. Réservé pour une utilisation ultérieure ; la valeur 0.

`pReferenceInfo`\
[out] Un [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) structure est remplie avec une description de la propriété.

## <a name="return-value"></a>Valeur de retour
 Retourne toujours `E_NOTIMPL`.

## <a name="see-also"></a>Voir aussi
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md)
- [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)