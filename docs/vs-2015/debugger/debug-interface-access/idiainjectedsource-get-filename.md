---
title: IDiaInjectedSource::get_filename | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_filename method
ms.assetid: 20f4fc68-335a-4971-b3a6-76501f0e8b19
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 68db108fe6193517d26957fd74807c2ed2b89035
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58947495"
---
# <a name="idiainjectedsourcegetfilename"></a>IDiaInjectedSource::get_filename
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Récupère le nom de fichier pour la source.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_filename (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 pRetVal  
 [out] Retourne le nom de fichier pour la source.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`. Retourne `S_FALSE` si cette propriété n’est pas pris en charge. Sinon, retourne un code d'erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)
