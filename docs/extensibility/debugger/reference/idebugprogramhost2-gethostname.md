---
title: IDebugProgramHost2::GetHostName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramHost2::GetHostName
helpviewer_keywords:
- IDebugProgramHost2::GetHostName
ms.assetid: 48bbb089-e59a-471a-9965-24b42a8dabf3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 26f88e6e955b83bf96b0664ffc6daba9a5430aa9
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203963"
---
# <a name="idebugprogramhost2gethostname"></a>IDebugProgramHost2::GetHostName
Obtient le titre, le nom convivial ou le nom de fichier du processus d’hébergement de ce programme.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetHostName( 
   DWORD dwType,
   BSTR* pbstrHostName
);
```

```csharp
int GetHostName( 
   uint dwType,
   out string pbstrHostName
);
```

## <a name="parameters"></a>Paramètres
`dwType`\
[in] Une valeur comprise entre le [GETHOSTNAME_TYPE](../../../extensibility/debugger/reference/gethostname-type.md) énumération.

`pbstrHostName`\
[out] Retourne le nom du processus d’hébergement demandé.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 Dans une implémentation classique de cette méthode, le `dwType` paramètre est ignoré et un nom convivial de l’ordinateur hôte est retourné. Une autre implémentation possible consiste à passer le `dwType` paramètre à un appel à la [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) méthode pour obtenir le nom.

## <a name="see-also"></a>Voir aussi
- [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)
- [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)