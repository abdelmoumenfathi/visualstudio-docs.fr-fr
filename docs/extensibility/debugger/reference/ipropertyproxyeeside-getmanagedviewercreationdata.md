---
title: IPropertyProxyEESide::GetManagedViewerCreationData | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
helpviewer_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
ms.assetid: c4eb4d60-8816-4d52-bc8d-dffd4f066499
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d8ae4a20735c02f564cbf5c749247ec16572c034
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66198822"
---
# <a name="ipropertyproxyeesidegetmanagedviewercreationdata"></a>IPropertyProxyEESide::GetManagedViewerCreationData
Récupère des informations sur la visionneuse pour ce type de propriété afin d’instancier cette visionneuse.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetManagedViewerCreationData(
   BSTR*                  assemName,
   IEEDataStorage**       assemBytes,
   IEEDataStorage**       assemPdb,
   BSTR*                  className,
   ASSEMBLYLOCRESOLUTION* alr,
   BOOL*                  replacementOk
);
```

```csharp
int GetManagedViewerCreationData(
   out string                     assemName,
   out IEEDataStorage             assemBytes,
   out IEEDataStorage             assemPdb,
   out string                     className,
   out enum_ASSEMBLYLOCRESOLUTION alr,
   out int                        replacementOk
);
```

## <a name="parameters"></a>Paramètres
`assemName`\
[out] Retourne le nom de l’assembly contenant cet objet.

`assemBytes`\
[out] Retourne un [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objet contenant les octets de l’assembly de cet objet (Ceci est une valeur null si aucun octet n’est disponible).

`assemPdb`\
[out] Retourne un `IEEDataStorage` objet contenant le symbole de stocker des informations pour cet objet (une valeur null si aucun magasin de symboles n’est disponible).

`className`\
[out] Retourne le nom de classe qui contient cet objet.

`alr`\
[out] Retourne une valeur de la [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) énumération indiquant l’emplacement de l’assembly.

`replacementOk`\
[out] Retourne la valeur différente de zéro (`TRUE`) si la valeur de cet objet peut être modifiée ; zéro (`FALSE`) si l’objet est en lecture seule.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
 Cette méthode est utilisée par les visualiseurs de type pour instancier une visionneuse gérée.

## <a name="see-also"></a>Voir aussi
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)