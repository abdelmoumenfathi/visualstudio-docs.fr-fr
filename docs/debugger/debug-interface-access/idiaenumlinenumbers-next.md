---
title: IDiaEnumLineNumbers::Next | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Next method
ms.assetid: 363d5b40-1316-4ab8-836f-63637f619e0a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 66abd987e3da4fadaac9d5b2de6664c4ae9e24ac
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62829756"
---
# <a name="idiaenumlinenumbersnext"></a>IDiaEnumLineNumbers::Next
Récupère un nombre spécifié de numéros de ligne dans la séquence d’énumération.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Next ( 
   ULONG            celt,
   IDiaLineNumber** rgelt,
   ULONG*           pceltFetched
);
```

#### <a name="parameters"></a>Paramètres
 celt

[in] Le nombre de numéros de ligne dans l’énumérateur à récupérer.

 rgelt

[out] Retourne un tableau de [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md) objets qui représentent les numéros de ligne souhaité.

 pceltFetched

[out] Retourne le nombre de numéros de ligne dans l’énumérateur extraite.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne `S_OK`. Retourne `S_FALSE` s’il en existe aucun numéro de ligne plus. Sinon, retourne un code d'erreur.

## <a name="see-also"></a>Voir aussi
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
- [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)