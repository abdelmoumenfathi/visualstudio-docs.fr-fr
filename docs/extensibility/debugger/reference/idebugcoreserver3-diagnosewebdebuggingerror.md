---
title: IDebugCoreServer3::DiagnoseWebDebuggingError | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
helpviewer_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 63d6bce43062996ae14c704908543b86adce2877
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66205540"
---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
Tente de déterminer pourquoi un auto-attach a échoué.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT DiagnoseWebDebuggingError(
   LPCWSTR pszUrl
);
```

```csharp
int DiagnoseWebDebuggingError(
   string pszUrl
);
```

## <a name="parameters"></a>Paramètres
`pszUrl`\
[in] Actuellement non utilisé ; doit toujours être défini sur une valeur null.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur. Autres codes de retour standard sont les suivantes :

|Code|Description|
|----------|-----------------|
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|Impossible de déterminer pourquoi le serveur distant a échoué démarrer le débogage.|
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|Impossible de déboguer sur un serveur distant, probablement en raison d’autorisations insuffisantes ou parce que l’exécution du verbe DEBUG n’est pas activé.|
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|Le serveur web a été verrouillé et bloque l’exécution du verbe DEBUG, ce qui est nécessaire pour activer le débogage.|

## <a name="see-also"></a>Voir aussi
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)