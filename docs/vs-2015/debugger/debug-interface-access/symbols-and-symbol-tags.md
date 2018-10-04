---
title: Balises Symbols et Symbol | Microsoft Docs
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
- symbols [DIA SDK]
ms.assetid: 2ee3a262-cda6-48bf-b799-a37edde6c8b8
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04dfbe961b122ded6ddb5ff19d70091ba6c408c0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47502791"
---
# <a name="symbols-and-symbol-tags"></a>Balises Symbols et Symbol
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [balises Symbols et Symbol](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/symbols-and-symbol-tags).  
  
Les informations de débogage sur un programme compilé sont stockées dans le fichier de base de données (.pdb) du programme en tant que symboles qui sont accessibles à l’aide de l’API du Kit de développement logiciel Debug Interface Access (DIA). Tous les symboles ont un [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) et un [IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md) propriété. Le `symTag` propriété indique le type de symbole, tel que défini par le [SymTagEnum (énumération)](../../debugger/debug-interface-access/symtagenum.md) énumération. Le `symIndexId` propriété est un `DWORD` valeur qui contient l’identificateur unique pour chaque instance d’un symbole.  
  
 Les symboles ont également des propriétés que vous peuvent spécifier des informations supplémentaires sur le symbole, ainsi que des références à d’autres symboles, plus souvent un [IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md) ou [IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md). Lorsque vous interrogez une propriété qui contient une référence, la référence est renvoyée comme un [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) objet. Ces propriétés sont toujours associées à une autre propriété par le même nom mais avec le suffixe avec « Id », par exemple, [IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md) et [IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md). Les tables dans [emplacements de symboles](../../debugger/debug-interface-access/symbol-locations.md), [hiérarchie lexicale des Types de symboles](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md), et [hiérarchie de classe de Types de symboles](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md) décrit les propriétés pour chacun des différents types de symboles. Ces propriétés peuvent avoir des informations pertinentes sur ou des références à d’autres symboles. Étant donné que le `*Id` propriétés sont des identificateurs ordinales simplement numériques de leurs propriétés connexes, ils sont omis d’autres discussions. Ces autorisations sont désignées uniquement lorsque cela est nécessaire pour clarification de paramètre.  
  
 Lorsque vous tentez d’accéder à la propriété, si aucune erreur ne se produit et une valeur a été attribuée à la propriété de symbole, de la propriété « get » retourne de la méthode `S_OK`. La valeur de retour `S_FALSE` indique que la propriété n’est pas valide pour le symbole actuel.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Emplacements des symboles](../../debugger/debug-interface-access/symbol-locations.md)  
 Décrit les différents types d’emplacements qu'un symbole peut avoir.  
  
 [Hiérarchie lexicale des types de symboles](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)  
 Décrit les types de symboles qui forment les hiérarchies lexicales telles que les fichiers, les modules et fonctions.  
  
 [Hiérarchie de classes des types de symboles](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)  
 Décrit les types de symboles qui correspondent aux différents éléments de langage telles que les types de retour de fonction, des tableaux et des classes.  
  
## <a name="see-also"></a>Voir aussi  
 [SDK Debug Interface Access](../../debugger/debug-interface-access/debug-interface-access-sdk.md)


