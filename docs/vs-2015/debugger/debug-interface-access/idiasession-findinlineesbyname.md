---
title: IDiaSession::findInlineesByName | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9860336d-f703-4ecb-bfc4-3f5beb175a76
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6c2b540303c3f31f7f6088f2ab9721b1237efbac
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58953872"
---
# <a name="idiasessionfindinlineesbyname"></a>IDiaSession::findInlineesByName
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Récupère une énumération qui permet au client d’effectuer une itération dans les informations de numéro de ligne de toutes les fonctions inline qui correspondent à un nom spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT findInlineesByName (   
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `name`  
 [in] Spécifie le nom à utiliser pour comparaison.  
  
 `option`  
 [in] Spécifie les options de comparaison appliquées à la recherche de nom. Les valeurs de la [NameSearchOptions (énumération)](../../debugger/debug-interface-access/namesearchoptions.md) énumération peut être utilisée seul ou combiné.  
  
 `ppResult`  
 [out] Retourne un [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) objet qui contient une liste des numéros de ligne qui ont été récupérées.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum, énumération](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
