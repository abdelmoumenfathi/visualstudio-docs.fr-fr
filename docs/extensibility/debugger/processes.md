---
title: Processus | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1453aadebfaacb6ff4232f02eb22d4e69a94c840
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925284"
---
# <a name="processes"></a>Processus
Dans l’architecture du débogueur, une *processus*:

- Est un conteneur pour un ensemble de programmes. Il est très similaire à un processus Windows, qui est un conteneur pour un ensemble de threads.

- Peut s’identifier par son nom, identificateur ou identificateur physique.

- Pouvez énumérer tous les programmes en cours d’exécution (et leurs threads).

- Peut décrire elle-même, le port, dans qu'il est en cours d’exécution, ainsi que l’ordinateur qui le contient.

- Peut créer un ou plusieurs programmes, mettre fin à tous les programmes qu’il crée ou provoquer un blocage du programme.

- Est représenté par un [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) interface, qui est créé lorsque le processus est lancé. Un processus est exécuté par le Gestionnaire de débogage de session (SDM) ou [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).

  Le package de débogage peut attacher un moteur de débogage (dé) à un processus en appelant [attacher](../../extensibility/debugger/reference/idebugprocess2-attach.md), ce qui signifie que l’Allemagne s’attache à tous les programmes possible en cours d’exécution dans le processus qu’il peut traiter. Par exemple, si le common language runtime DE joint à un processus, il se connecte uniquement à des programmes qui sont en cours d’exécution du code managé.

## <a name="see-also"></a>Voir aussi
- [Programmes](../../extensibility/debugger/programs.md)
- [Threads](../../extensibility/debugger/threads.md)
- [Concepts du débogueur](../../extensibility/debugger/debugger-concepts.md)
- [Déboguer le package](../../extensibility/debugger/debug-package.md)
- [Moteur de débogage](../../extensibility/debugger/debug-engine.md)
- [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)
- [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)
- [Attacher](../../extensibility/debugger/reference/idebugprocess2-attach.md)