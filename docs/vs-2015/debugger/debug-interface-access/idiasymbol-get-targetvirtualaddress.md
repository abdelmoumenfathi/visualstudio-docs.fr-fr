---
title: IDiaSymbol::get_targetVirtualAddress | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_targetVirtualAddress method
ms.assetid: a0a5ce72-95f8-443e-bb4b-8c21194faad0
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6ac721e01852481521a7252dd4d6337f270e242d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47504613"
---
# <a name="idiasymbolgettargetvirtualaddress"></a>IDiaSymbol::get_targetVirtualAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [IDiaSymbol::get_targetVirtualAddress](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-targetvirtualaddress).  
  
Récupère l’adresse virtuelle (VA) d’une cible de conversion de code.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_targetVirtualAddress (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pRetVal`  
 [out] Retourne l’évaluation des vulnérabilités d’une cible de conversion de code.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne `S_FALSE` ou un code d’erreur.  
  
> [!NOTE]
>  La valeur de retour `S_FALSE` signifie que la propriété n’est pas disponible pour le symbole.  
  
## <a name="remarks"></a>Notes  
 Cette propriété est valide uniquement si le symbole comme un [SymTagEnum (énumération)](../../debugger/debug-interface-access/symtagenum.md) valeur `SymTagThunk`.  
  
 Une conversion de « code » est un morceau de code qui effectue la conversion entre un espace d’adressage de mémoire de 32 bits (également appelé espace d’adresse plat) et un espace d’adressage de 16 bits (appelé un espace d’adressage segmentés).  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum, énumération](../../debugger/debug-interface-access/symtagenum.md)


