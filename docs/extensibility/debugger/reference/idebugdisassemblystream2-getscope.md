---
title: IDebugDisassemblyStream2::GetScope | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::GetScope
helpviewer_keywords:
- IDebugDisassemblyStream2::GetScope
ms.assetid: 71c6e632-642a-42d8-a995-77e4ac190a5b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4a9da518d36c570bd53fa44118972366f9bf6ab4
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66204942"
---
# <a name="idebugdisassemblystream2getscope"></a>IDebugDisassemblyStream2::GetScope
Obtient la portée du flux de code machine.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetScope( 
   DISASSEMBLY_STREAM_SCOPE* pdwScope
);
```

```csharp
int GetScope( 
   out enum_ DISASSEMBLY_STREAM_SCOPE pdwScope
);
```

## <a name="parameters"></a>Paramètres
`pdwScope`\
[out] Retourne une valeur de la [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) énumération qui décrit l’étendue de ce flux de code machine.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 L’étendue d’un code machine peut être une fonction ou l’ensemble du module, par exemple.

## <a name="see-also"></a>Voir aussi
- [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)
- [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md)