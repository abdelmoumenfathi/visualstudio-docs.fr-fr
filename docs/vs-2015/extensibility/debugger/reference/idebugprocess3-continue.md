---
title: IDebugProcess3::Continue | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProcess3::Continue
helpviewer_keywords:
- IDebugProcess3::Continue
ms.assetid: 57506242-5763-4c08-adb9-8a78ce02cebb
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8e7167a5425566936c196960d5014fcf5d7c8709
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63405835"
---
# <a name="idebugprocess3continue"></a>IDebugProcess3::Continue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Continue ce processus en cours d’exécution à partir d’un état arrêté. N’importe quel état de l’exécution précédente (par exemple, une étape) est conservé, et le processus commence à s’exécuter à nouveau.  
  
> [!NOTE]
> Cette méthode doit être utilisée à la place de [continuer](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Continue(  
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Continue(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pThread`  
 [in] Un [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objet qui représente le thread de se poursuivre.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne le code d’erreur.  
  
## <a name="remarks"></a>Notes  
 Cette méthode est appelée sur ce processus, quel que soit le nombre de processus est en cours de débogage, ou le processus qui a généré l’événement de l’arrêt. L’implémentation doit conserver l’état de l’exécution précédente (par exemple, une étape) et poursuivre l’exécution comme s’il n’avait jamais arrêté avant la fin de sa précédente exécution. Autrement dit, si un thread dans ce processus a été effectuant une opération de pas à pas principal, a été arrêté car un autre processus s’est arrêté, puis `Continue` a été appelée, le texte spécifié thread doit terminer l’opération de pas à pas principal d’origine.  
  
 **Avertissement** n’envoient pas d’un événement d’arrêt ou un événement (synchrone) immédiat [événement](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) lors du traitement de cet appel ; sinon, le débogueur peut se bloquer.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
