---
title: IDebugBinder3::GetTypeArguments | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugBinder3::GetTypeArguments
helpviewer_keywords:
- IDebugBinder3::GetTypeArguments method
ms.assetid: fa0c37a7-327f-463e-9a9d-bb3f534584cb
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1f7b6038013370ad85a665d9899d367e621aa991
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58948545"
---
# <a name="idebugbinder3gettypearguments"></a>IDebugBinder3::GetTypeArguments
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]
Cette méthode récupère une liste des types d’arguments associée à cet objet.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetTypeArguments(
   UINT          skip,
   UINT          count,
   IDebugField** ppFields,
   UINT*         pFetched
);
```

```csharp
int GetTypeArguments(
   uint          skip,
   uint          count,
   IDebugField[] ppFields,
   out uint      pFetched
);
```

#### <a name="parameters"></a>Paramètres

 `skip`

 [in] Nombre de champs à ignorer avant d’obtenir les types d’arguments.

 `count`

 [in] Le nombre de champs de l’argument à retourner (spécifie également la taille de la `ppFields` tableau).

 `ppFields`

 [in, out] Un tableau de champs renseignés au retour de cette méthode.

 `pFetched`

 [out] Le nombre de champs de type d’argument que vous souhaitez réellement retournés (facultatif).

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 Le nombre de types d’arguments peut être obtenu au préalable avec [GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md).

## <a name="see-also"></a>Voir aussi

- [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)
- [GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)