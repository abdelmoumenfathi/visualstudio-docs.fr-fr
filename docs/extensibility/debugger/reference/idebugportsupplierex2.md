---
title: IDebugPortSupplierEx2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortSupplierEx2 interface
ms.assetid: dae0050a-a50a-4f35-bfbd-e538f537b20f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a87ec52c3c7929d32da2b568b8e2735efc6319d8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62917925"
---
# <a name="idebugportsupplierex2"></a>IDebugPortSupplierEx2
Prend en charge pour un fournisseur de port sélectionner et d’interagir avec un serveur de base.

## <a name="syntax"></a>Syntaxe

```
IDebugPortSupplierEx2 : IUnknown
```

## <a name="notes-for-implementers"></a>Notes de publication pour les implémenteurs
 Un fournisseur de port personnalisé implémente cette interface afin qu’elle peut sélectionner le serveur de base à utiliser.

## <a name="methods"></a>Méthodes
 Le tableau suivant présente les méthodes de **IDebugPortSupplierEx2**.

|Méthode|Description|
|------------|-----------------|
|[SetServer](../../../extensibility/debugger/reference/idebugportsupplierex2-setserver.md)|Définit le serveur de base pour le fournisseur de port.|

## <a name="requirements"></a>Configuration requise
 En-tête : Portpriv.h

 Espace de noms : Microsoft.VisualStudio.Debugger.Interop

 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Interfaces de base](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)