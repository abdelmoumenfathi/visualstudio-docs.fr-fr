---
title: IDebugEngine2::GetEngineID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::GetEngineID
helpviewer_keywords:
- IDebugEngine2::GetEngineID
ms.assetid: 0d5674c8-a9b9-4b72-8211-d2d68695775a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 965a674c0586f4b61c934570638f5168a0ab0bb4
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66207623"
---
# <a name="idebugengine2getengineid"></a>IDebugEngine2::GetEngineID
Obtient le GUID du moteur de débogage (dé).

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEngineID(
    GUID* pguidEngine
);
```

```csharp
int GetEngineID(
    out Guid pguidEngine
);
```

## <a name="parameters"></a>Paramètres
`pguidEngine`\
[out] Retourne le GUID de l’Allemagne.

## <a name="return-value"></a>Valeur de retour
En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
Voici quelques exemples de GUID typique `guidScriptEng`, `guidNativeEng`, ou `guidSQLEng`. Nouveaux moteurs de débogage seront créer leur propre GUID pour l’identification.

## <a name="example"></a>Exemple
L’exemple suivant montre comment implémenter cette méthode pour une simple `CEngine` objet qui implémente le [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) interface.

```cpp
HRESULT CEngine::GetEngineId(GUID *pguidEngine) {
    if (pguidEngine) {
        // Set pguidEngine to guidBatEng, as defined in the Batdbg.idl file.
        // Other languages would require their own guidDifferentEngine to be
        //defined in the Batdbg.idl file.
        *pguidEngine = guidBatEng;
        return NOERROR; // This is typically S_OK.
    } else {
        return E_INVALIDARG;
    }
}
```

## <a name="see-also"></a>Voir aussi
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
