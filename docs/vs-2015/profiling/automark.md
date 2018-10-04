---
title: AutoMark | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e01dac3f1012c76ebe6095b5b5a244226fe4843
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47495170"
---
# <a name="automark"></a>AutoMark
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [AutoMark](https://docs.microsoft.com/visualstudio/profiling/automark).  
  
L’option **AutoMark** spécifie le nombre de millisecondes écoulées entre les collectes des événements des compteurs de performances logiciels Windows. Les compteurs de performances Windows sont spécifiés dans l’option **WinCounter**.  
  
 Vous ne pouvez spécifier qu’une seule option **AutoMark** sur la ligne de commande. Notez que l’intervalle d’échantillonnage de **WinCounter** spécifié par **AutoMark** est indépendant de l’intervalle d’échantillonnage principal.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Milliseconds`  
 Spécifie le nombre de millisecondes écoulées entre les collectes des événements des compteurs de performances Windows.  
  
## <a name="required-options"></a>Options obligatoires  
 **WinCounter:** `Path`  
 Spécifie le compteur de performances Windows à collecter. Quand vous utilisez la méthode d’instrumentation, vous pouvez spécifier plusieurs compteurs Windows. Quand vous utilisez la méthode d’échantillonnage, vous ne pouvez spécifier qu’un seul compteur Windows. L’option **WinCounter** doit être spécifiée dans une ligne de commande qui contient l’option **Start**.  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, un intervalle d’échantillonnage de 1 000 millisecondes est défini pour deux compteurs de performances Windows.  
  
```  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Voir aussi  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilage d’applications autonomes](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilage d’applications web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilage de services](../profiling/command-line-profiling-of-services.md)


