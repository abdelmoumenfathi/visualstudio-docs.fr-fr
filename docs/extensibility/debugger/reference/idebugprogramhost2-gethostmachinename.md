---
title: IDebugProgramHost2::GetHostMachineName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramHost2::GetHostMachineName
helpviewer_keywords:
- IDebugProgramHost2::GetHostMachineName
ms.assetid: 4677ffe4-aa9b-4450-a63b-74cd3984d956
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: acdc2bc8bf92604994acc32e98e4dca5b58f1b05
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203974"
---
# <a name="idebugprogramhost2gethostmachinename"></a>IDebugProgramHost2::GetHostMachineName
Obtient le nom de l’ordinateur que le processus qui héberge ce programme est en cours d’exécution.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetHostMachineName( 
   BSTR* pbstrHostMachineName
);
```

```csharp
int GetHostMachineName( 
   out string pbstrHostMachineName
);
```

## <a name="parameters"></a>Paramètres
`pbstrHostMachineName`\
[out] Retourne le nom de l’ordinateur.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="see-also"></a>Voir aussi
- [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)