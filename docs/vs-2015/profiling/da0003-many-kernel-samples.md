---
title: 'DA0003 : Nombreux échantillons de noyau | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.rules.DA0003
- vs.performance.DA0003
- vs.performance.3
- vs.performance.rules.DAManyKernelSamples
ms.assetid: c1f46f77-eb95-42e5-b340-d86bc9de41b4
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ad9a0671595d4628932ff4f2db41a137e060c4d1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60076483"
---
# <a name="da0003-many-kernel-samples"></a>DA0003 : Nombreux échantillons de noyau
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Id de règle | DA0003 |  
| Catégorie | Utilisation des outils de profilage |  
| Méthodes de profilage | Échantillonnage |  
| Message | Vous avez une proportion élevée d’échantillons en Mode noyau. Ceci peut indiquer un volume élevé d’activité d’E/S ou un taux élevé de changements de contexte. Envisagez de reprofiler votre application avec le mode Instrumentation.|  
| Type de règle | Informations |  
  
## <a name="cause"></a>Cause  
 Une proportion importante des échantillons de pile des appels qui ont été collectés pour l’application s’exécutaient en mode noyau. Envisagez de profiler votre application avec une autre méthode de profilage.  
  
## <a name="rule-description"></a>Description de la règle  
 Dans Windows, le code peut être exécuté en mode noyau ou en mode utilisateur. (Le mode noyau est également appelé mode privilégié.) Seul le code système de bas niveau, par exemple un pilote de périphérique, s’exécute en mode noyau. Une application en mode utilisateur peut passer en mode noyau pour effectuer des opérations d’E/S, pour attendre des primitives de synchronisation de thread ou de processus, ou pour effectuer des appels système.  
  
 L’échantillonnage est plus efficace quand vous profilez des applications qui passent la majeure partie de leur temps à travailler en mode utilisateur. Le nombre d’échantillons qui ont été recueillis quand l’application s’exécutait en mode noyau peut indiquer des opérations d’E/S fréquentes ou que des changements de contexte se produisent. Aucune de ces opérations ne peut être examinée avec la méthode d’échantillonnage. Si trop grand nombre d’échantillons en mode noyau sont pris, les données d’échantillonnage peuvent ne pas contenir suffisamment d’échantillons en mode utilisateur pour être statistiquement significatives.  
  
## <a name="how-to-fix-violations"></a>Comment corriger les violations  
 Envisagez de reprofiler votre application avec une des options suivantes :  
  
- Profilez avec la méthode d’instrumentation.  
  
- Augmentez le taux d’échantillonnage pour essayer de collecter plus d’échantillons en mode utilisateur.
