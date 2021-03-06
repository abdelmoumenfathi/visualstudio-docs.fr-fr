---
title: Débogage du Code GPU | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: c7e77a5a-cb57-4b11-9187-ecc89acc8775
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ea3286c2d4ae27afc7422700bd4f745ab28520fa
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399439"
---
# <a name="debugging-gpu-code"></a>Débogage du code GPU
Vous pouvez déboguer du code C++ qui s'exécute sur l'unité de traitement graphique (GPU). La prise en charge du débogage GPU dans Visual Studio inclut la détection de concurrence, les processus de lancement et leur attachement, ainsi que l'intégration dans les fenêtres de débogage.

## <a name="supported-platforms"></a>Plateformes prises en charge
 Le débogage est pris en charge sur [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[win8](../debugger/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)] et [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)]. Pour effectuer un débogage sur l'émulateur de logiciel, [!INCLUDE[win8](../debugger/includes/win8_md.md)] ou [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)] est requis. Pour effectuer un débogage sur le matériel, vous devez installer les pilotes de votre carte graphique. Tous les fournisseurs de matériel n'implémentent pas toutes les fonctionnalités de débogage. Consultez la documentation du fournisseur pour connaître les limitations.

> [!NOTE]
> Les fournisseurs de matériel indépendants qui souhaitent prendre en charge le débogage GPU dans Visual Studio doivent créer une DLL qui implémente l'interface VSD3DDebug pour cibler leurs propres pilotes.

## <a name="configuring-gpu-debugging"></a>Configuration du débogage GPU
 Le débogueur ne peut pas s'arrêter sur le code UC et le code GPU dans la même exécution d'application. Par défaut, le débogueur s'arrête sur le code UC. Pour déboguer le code GPU, utilisez l'une de ces deux étapes :

- Dans la liste **Type de débogage** sur la barre d’outils **Standard**, choisissez **GPU uniquement**.

- Dans l’**Explorateur de solutions**, dans le menu contextuel du projet, choisissez **Propriétés**. Dans la boîte de dialogue **Pages de propriétés**, sélectionnez **Débogage**, puis sélectionnez **GPU uniquement** dans la liste **Type de débogueur**.

## <a name="launching-and-attaching-to-applications"></a>Lancement et attachement des applications
 Vous pouvez utiliser les commandes de débogage Visual Studio pour démarrer et arrêter le débogage GPU. Pour plus d’informations, consultez [Naviguer dans le code avec le débogueur](../debugger/navigating-through-code-with-the-debugger.md). Vous pouvez également attacher le débogueur GPU à un processus en cours d'exécution, mais uniquement si ce processus exécute le code GPU. Pour plus d’informations, consultez [attacher aux processus en cours d’exécution](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).

## <a name="run-current-tile-to-cursor-and-run-to-cursor"></a>Exécuter le tile actuel au curseur et Exécuter jusqu'au curseur
 Lorsque vous déboguez sur le GPU, vous disposez de deux options pour accéder à l'emplacement du curseur. Les commandes pour les deux options sont disponibles dans le menu contextuel de l'éditeur de code.

1. La commande **Exécuter jusqu’au curseur** exécute votre application jusqu’à l’emplacement du curseur, puis s’arrête. Cela ne signifie pas que le thread en cours s'exécute jusqu'au curseur, mais plutôt que le premier thread qui atteint le point du curseur déclenche l'interruption. Consultez [naviguer dans le Code avec le débogueur](../debugger/navigating-through-code-with-the-debugger.md)

2. La commande **Exécuter le tile actuel au curseur** exécute votre application jusqu’à ce que tous les threads de la mosaïque active atteignent le curseur, puis s’interrompt.

## <a name="debugging-windows"></a>Fenêtres de débogage
 L'utilisation de certaines fenêtres de débogage vous permet d'examiner, de marquer et de geler des threads GPU. Pour plus d'informations, voir :

- [Utilisation de la fenêtre Piles parallèles](../debugger/using-the-parallel-stacks-window.md)

- [Utilisation de la fenêtre Tâches](../debugger/using-the-tasks-window.md)

- [Guide pratique pour utiliser la fenêtre Espion parallèle](../debugger/how-to-use-the-parallel-watch-window.md)

- [Déboguer les Threads et processus](../debugger/debug-threads-and-processes.md) (barre d’outils emplacement de débogage)

- [Guide pratique pour utiliser la fenêtre Threads GPU](../debugger/how-to-use-the-gpu-threads-window.md)

## <a name="data-synchronization-exceptions"></a>Exceptions de synchronisation de données
 Le débogueur peut identifier plusieurs conditions de synchronisation de données pendant l’exécution. Lorsqu'une condition est détectée, le débogueur passe à l'état d'arrêt. Vous disposez de deux options : **Arrêter** ou **Continuer**. À l’aide de la boîte de dialogue **Exceptions**, vous pouvez configurer si le débogueur détecte ces conditions, mais également les conditions pour lesquelles il s’arrêtera. Pour plus d’informations, consultez [la gestion des Exceptions avec le débogueur](../debugger/managing-exceptions-with-the-debugger.md). Vous pouvez également utiliser la boîte de dialogue **Options** pour spécifier que le débogueur doit ignorer les exceptions si les données écrites ne modifient pas la valeur des données. Pour plus d’informations, consultez [Général, Débogage, Boîte de dialogue Options](../debugger/general-debugging-options-dialog-box.md).

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="specifying-an-accelerator"></a>Spécification d'un accélérateur
 Les points d’arrêt dans le code GPU sont uniquement atteints si le code s’exécute sur l’accélérateur [accelerator::direct3d_ref](/cpp/parallel/amp/reference/accelerator-class#direct3d_ref) (REF). Si vous ne spécifiez aucun accélérateur dans votre code, l’accélérateur REF est automatiquement sélectionné comme **Type d’accélérateur de débogage** dans les propriétés du projet. Si votre code sélectionne explicitement un accélérateur, l'accélérateur REF ne sera pas utilisé pendant le débogage et les points d'arrêt ne seront pas atteints tant que votre matériel GPU disposera de la prise en charge du débogage. Vous pouvez y remédier dans la rédaction du code afin qu'il utilise l'accélérateur REF pendant le débogage. Pour plus d’informations, consultez Propriétés du projet et [à l’aide des objets accelerator et accelerator_view](/cpp/parallel/amp/using-accelerator-and-accelerator-view-objects) et [paramètres de projet pour un C++ Configuration Debug](../debugger/project-settings-for-a-cpp-debug-configuration.md).

### <a name="conditional-breakpoints"></a>Points d'arrêt conditionnels
 Les points d'arrêt conditionnels dans le code GPU sont pris en charge, mais chaque expression ne peut pas être évaluée sur le périphérique. Lorsqu'une expression ne peut pas être évaluée sur le périphérique, elle est évaluée dans le débogueur. Le débogueur risque de s'exécuter plus lentement que le périphérique.

### <a name="error-there-is-a-configuration-issue-with-the-selected-debugging-accelerator-type"></a>Erreur : Il existe un problème de configuration avec le Type d’accélérateur de débogage sélectionné.
 Cette erreur se produit en cas d'incohérence entre les paramètres du projet et la configuration du PC que vous déboguez. Pour plus d’informations, consultez [paramètres de projet pour une Configuration Debug C++](../debugger/project-settings-for-a-cpp-debug-configuration.md).

### <a name="error-the-debug-driver-for-the-selected-debugging-accelerator-type-is-not-installed-on-the-target-machine"></a>Erreur : Le pilote de débogage pour le Type d’accélérateur de débogage sélectionné n’est pas installé sur l’ordinateur cible.
 Cette erreur se produit si vous effectuez un débogage sur un ordinateur distant. Le débogueur ne peut pas déterminer avant l'exécution si les pilotes sont installés sur l'ordinateur distant. Les pilotes sont disponibles auprès du fabricant de la carte graphique.

### <a name="error-timeout-detection-and-recovery-tdr-must-be-disabled-at-the-remote-site"></a>Erreur : Détection de délai d’attente et de récupération (TDR) doivent être désactivées sur le site distant.
 Les calculs C++ AMP peuvent dépasser l'intervalle de temps par défaut qui est défini par le processus Windows TDR. Lorsque cela se produit, le calcul est annulé et les données sont perdues. Pour plus d’informations, consultez [Handling TDRs in C++ AMP](http://go.microsoft.com/fwlink/p/?LinkId=249154).

## <a name="see-also"></a>Voir aussi
- [Procédure pas à pas : Débogage d’une application C++ AMP](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)
- [Paramètres de projet pour une configuration Debug C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)
- [Start GPU Debugging in Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=255381)