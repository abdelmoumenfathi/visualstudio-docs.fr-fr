---
title: IDiaSymbol::get_addressSection | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_addressSection method
ms.assetid: fe80d479-3bb5-4f55-9b62-1bd58d0a60ce
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f4ae24a194050868e1e2efbc5d29e7cf20e6cf5d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63402379"
---
# <a name="idiasymbolgetaddresssection"></a>IDiaSymbol::get_addressSection
Récupère la partie de la section d’une adresse d’emplacement. Quand utiliser le [LocationType (énumération)](../../debugger/debug-interface-access/locationtype.md) est défini sur `LocIsStatic`.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_addressSection ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Paramètres
 `pRetVal`

[out] Retourne la partie de la section d’une adresse d’emplacement.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`; sinon, retourne `S_FALSE` ou un code d’erreur.

> [!NOTE]
> La valeur de retour `S_FALSE` signifie que la propriété n’est pas disponible pour le symbole.

## <a name="remarks"></a>Notes
 Pour les membres statiques sont situés dans une DLL externe, la section retournée par cette méthode peut être 0 car cette méthode repose sur l’obtention de l’adresse virtuelle du membre. Adresses virtuelles sont valides uniquement si le [IDiaSession::put_loadAddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) méthode dans le [IDiaSession](../../debugger/debug-interface-access/idiasession.md) interface a été appelée avec un paramètre différent de zéro en spécifiant l’adresse de chargement de la DLL.

 Pour obtenir la partie décalage d’une adresse, appelez le [IDiaSymbol::get_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md) (méthode).

## <a name="requirements"></a>Configuration requise

|Spécification|Description|
|-----------------|-----------------|
|En-tête :|dia2.h|
|Version :|DIA SDK v7.0|

## <a name="see-also"></a>Voir aussi
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [LocationType, énumération](../../debugger/debug-interface-access/locationtype.md)