---
title: Mise en route (SDK Debug Interface Access) | Microsoft Docs
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
- .dbg files
- DBG files
ms.assetid: cb3d040a-2846-40d7-bdbc-8a5beb5dd2f6
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 68b87c3789d0cc54f8492eed36c3028cf7a87df9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47496284"
---
# <a name="getting-started-debug-interface-access-sdk"></a>Mise en route (Kit de développement logiciel de Debug Interface Access)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [mise en route (Debug Interface Access SDK)](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/getting-started-debug-interface-access-sdk).  
  
Le Debug Interface Access (DIA) SDK vous fournit avec documentation pédagogique et un exemple qui illustre comment utiliser l’API de DIA. Utilisez les méthodes et interfaces dans le SDK DIA pour développer des applications personnalisées qui ouvrent les fichiers .pdb et .dbg et de rechercher leur contenu pour les symboles, les valeurs, les attributs, les adresses et les autres informations de débogage. Ce SDK fournit également des tables de référence pour les propriétés associées aux symboles utilisés dans les applications C++.  
  
 Pour mieux utiliser le DIA SDK, vous devez être familiarisé avec les éléments suivants :  
  
-   Langage de programmation C++  
  
-   Programmation COM.  
  
-   Environnement de développement intégré Visual Studio (IDE) pour compiler les exemples  
  
 Le SDK DIA est normalement installé avec Visual Studio et son emplacement par défaut est *[lecteur]* \Program Files\Microsoft 9.0\DIA Visual Studio SDK. Dans le cadre de l’installation, msdia90.dll, qui implémente le DIA SDK, est automatiquement enregistré tout ce que vous devez effectuer pour l’utiliser consiste donc à inclure `dia2.h` dans votre programme et un lien vers `diaguids.lib`.  
  
 En-tête : include\dia2.h  
  
 Bibliothèque : lib\diaguids.lib  
  
 DLL : bin\msdia80.dll  
  
 IDL : idl\dia2.idl  
  
## <a name="in-this-section"></a>Dans cette section  
 [Vue d’ensemble](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)  
 Passe en revue l’architecture de base de DIA.  
  
 [Interrogation du fichier .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 Fournit des instructions détaillées sur l’utilisation de l’API DIA pour interroger un fichier .pdb.  
  
## <a name="see-also"></a>Voir aussi  
 [SDK Debug Interface Access](../../debugger/debug-interface-access/debug-interface-access-sdk.md)


