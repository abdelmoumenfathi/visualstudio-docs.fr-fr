---
title: Onglet Général de traiter la boîte de dialogue Propriétés | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: 86f4d61d-a594-4aac-8960-c5279b4a10fd
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6116beb67baf072d9c9762a1e8c67408cc915f29
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62849816"
---
# <a name="general-tab-process-properties-dialog-box"></a>Onglet Général de la boîte de dialogue Propriétés du processus
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Utilisez le **général** onglet pour en savoir plus sur un processus spécifique. Pour afficher le [boîte de dialogue Propriétés de processus](../debugger/process-properties-dialog-box.md), déplacez le focus à un [vue processus](../debugger/processes-view.md) fenêtre. Sélectionnez n’importe quel nœud de processus dans l’arborescence, puis choisissez **propriétés** à partir de la **vue** menu.  
  
 Les paramètres suivants sont disponibles sur le **général** onglet :  
  
|Entrée|Description|  
|-----------|-----------------|  
|**Nom du module**|Nom du module.|  
|**ID du processus**|ID unique de ce processus. Numéros d’ID de processus sont réutilisés, donc ils identifient un processus uniquement pour la durée de vie du processus. Le type d’objet de processus est créé lorsqu’un programme est exécuté. Tous les threads dans un processus partagent le même espace d’adressage et ont accès aux mêmes données.|  
|**Priorité de base**|La priorité de base en cours de ce processus. Les threads d’un processus peuvent augmenter et réduire leur propre priorité de base par rapport à la priorité de base du processus.|  
|**Threads**|Le nombre de threads actuellement actifs dans ce processus.|  
|**Temps processeur**|Temps processeur total passé sur ce processus et ses threads. Égal à temps utilisateur plus temps privilégié.|  
|**Temps utilisateur**|Le temps total que les threads de ce processus ont passé à exécuter du code en Mode utilisateur dans des threads actifs. Applications s’exécutent en Mode utilisateur, tout comme les sous-systèmes tels que le Gestionnaire de fenêtres et le moteur de graphiques.|  
|**Temps privilégié**|Le temps total écoulé ce processus a été exécuté en Mode privilégié dans des threads actifs. La couche de service, les routines Executive et le noyau s’exécutent en Mode privilégié. Pilotes de périphérique pour la plupart des périphériques autres que les cartes graphiques et des imprimantes s’exécutent également en Mode privilégié. Certains travaux par Windows pour votre application peut-être apparaître dans d’autres processus de sous-système en plus de temps privilégié.|  
|**Temps écoulé**|Le temps total écoulé que ce processus a été exécuté.|
