---
title: IDebugProcess3::Step | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProcess3::Step
helpviewer_keywords:
- IDebugProcess3::Step
ms.assetid: 6ad9094c-27cc-4927-8a7c-1b4d97b2e436
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 45f60aaac3b89b7273a5f548b4716b6aee392256
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63405598"
---
# <a name="idebugprocess3step"></a>IDebugProcess3::Step
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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
  
#### <a name="parameters"></a>Paramètres  
 `pThread`  
 [in] Un [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objet qui représente le thread en cours en escalier.  
  
 `sk`  
 [in] Parmi les [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) valeurs.  
  
 `step`  
 [in] Parmi les [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) valeurs.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne S_OK ; sinon retourne le code d’erreur.  
  
## <a name="remarks"></a>Notes  
 En cas de toute synchronisation de threads ou de la communication entre les threads, les autres threads dans le processus doivent s’exécuter lorsqu’un thread particulier est exécution pas à pas.  
  
 **Avertissement** n’envoient pas d’un événement d’arrêt ou un événement (synchrone) immédiat [événement](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) lors du traitement de cet appel ; sinon, le débogueur peut se bloquer.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md)   
 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
