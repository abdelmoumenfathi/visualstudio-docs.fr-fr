---
title: IDebugProcess3::Step | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::Step
helpviewer_keywords:
- IDebugProcess3::Step
ms.assetid: 6ad9094c-27cc-4927-8a7c-1b4d97b2e436
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 24adde5d1c1a89949861481a3d370219875c2eb1
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66210953"
---
# <a name="idebugprocess3step"></a>IDebugProcess3::Step
Oblige le processus à l’étape d’une instruction ou une instruction.

> [!NOTE]
> Cette méthode doit être utilisée à la place de [étape](../../../extensibility/debugger/reference/idebugprogram2-step.md).

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Step(
   IDebugThread2* pThread,
   STEPKIND       sk,
   STEPUNIT       step,
);
```

```csharp
int Step(
   IDebugThread2 pThread,
   enum_STEPKIND sk,
   enum_STEPUNIT step
);
```

## <a name="parameters"></a>Paramètres
`pThread`\
[in] Un [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objet qui représente le thread en cours en escalier.

`sk`\
[in] Parmi les [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) valeurs.

`step`\
[in] Parmi les [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) valeurs.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne S_OK ; sinon retourne le code d’erreur.

## <a name="remarks"></a>Notes
 En cas de toute synchronisation de threads ou de la communication entre les threads, les autres threads dans le processus doivent s’exécuter lorsqu’un thread particulier est exécution pas à pas.

 **Avertissement** n’envoient pas d’un événement d’arrêt ou un événement (synchrone) immédiat [événement](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) lors du traitement de cet appel ; sinon, le débogueur peut se bloquer.

## <a name="see-also"></a>Voir aussi
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [STEPKIND](../../../extensibility/debugger/reference/stepkind.md)
- [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)