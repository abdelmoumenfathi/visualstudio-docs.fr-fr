---
title: Tâches de débogage | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], tasks
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 299db84fb06679bfbf9dff92234c944cbdec6295
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925815"
---
# <a name="debug-tasks"></a>Déboguer des tâches
Pour déboguer un programme, il doit être lancé et un moteur de débogage (dé) doit être attaché à celui-ci, sans quoi le DE doit être attaché à un programme lancé précédemment. Une fois attaché, le DE doit générer certains événements de démarrage. En réponse, le package de débogage tente de lier les points d’arrêt définis dans l’IDE. Quand le programme atteint un point d’arrêt lié, il s’arrête et attend une saisie de l’utilisateur.

## <a name="in-this-section"></a>Dans cette section
 [Problèmes de sécurité](../../extensibility/debugger/security-issues.md) présente les étapes de sécurité qui sont nécessaires pour déboguer un programme.

 [Lancer un programme](../../extensibility/debugger/launching-a-program.md) fournit des instructions détaillées sur la façon de spécifier un DE, qui appelle le système d’exploitation pour lancer le programme.

 [Attacher directement à un programme](../../extensibility/debugger/attaching-directly-to-a-program.md) décrit le processus utilisé pour déboguer un programme dans un processus qui est déjà en cours d’exécution.

 [Envoyer des événements de démarrage après un lancement](../../extensibility/debugger/sending-startup-events-after-a-launch.md) répertorie les événements qui ont lieu une fois que l’Allemagne est attaché au programme, jusqu'à ce que le programme est à son point d’entrée principal et est prêt pour le débogage.

 [Contrôle de l’exécution](../../extensibility/debugger/control-of-execution.md) explique comment le DE généralement envoie un événement de point d’entrée, un événement de fin de charge ou un événement d’arrêt en cours, selon les circonstances.

 [Lier des points d’arrêt](../../extensibility/debugger/binding-breakpoints.md) décrit comment, si l’utilisateur définit un point d’arrêt, l’IDE formule la demande et vous invite à entrer la session de débogage pour créer le point d’arrêt.

 [Évaluer les expressions](../../extensibility/debugger/evaluating-expressions.md) explique comment les expressions sont créées et que se passe-t-il lorsqu’une expression est évaluée.

 [Visualiser et afficher les données](../../extensibility/debugger/visualizing-and-viewing-data.md) explique comment les visualiseurs de type et les visionneuses personnalisées sont prises en charge par l’évaluateur d’expression (EE).

## <a name="related-sections"></a>Rubriques connexes
 [Concepts du débogueur](../../extensibility/debugger/debugger-concepts.md) décrit les principaux concepts architectures débogage.

 [Composants du débogueur](../../extensibility/debugger/debugger-components.md) fournit une vue d’ensemble de composants, qui incluent l’Allemagne, EE et le Gestionnaire de symboles (es) de débogage de Visual Studio.

 [Contextes du débogueur](../../extensibility/debugger/debugger-contexts.md) explique comment le D’opère simultanément dans des contextes d’évaluation code, documentation et expression. Décrit, pour chacun des trois contextes, emplacement, position ou d’évaluation pertinente à ce dernier.

## <a name="see-also"></a>Voir aussi
 [Bien démarrer](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)