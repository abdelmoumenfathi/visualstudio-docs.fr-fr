---
title: Mesurer l’utilisation du processeur à partir de la ligne de commande
description: Mesurez les performances du processeur dans votre application à partir de la ligne de commande.
ms.custom: ''
ms.date: 02/19/2019
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools, command-line
- Diagnostics Tools, command-line
- CPU Usage, command-line
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: '>= vs-2019'
ms.workload:
- multiple
ms.openlocfilehash: 87bf0c236f34e753866ea114dfc7f45e8f16a979
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62972414"
---
# <a name="measure-application-performance-from-the-command-line"></a>Mesurer les performances d’une application à partir de la ligne de commande

Vous pouvez collecter des informations sur le niveau de performance d’une application à l’aide d’outils en ligne de commande.

Dans l’exemple décrit dans cet article, vous collectez des informations sur le niveau de performance du Bloc-notes Microsoft, mais la même méthode peut servir à profiler n’importe quel processus.

## <a name="prerequisites"></a>Prérequis

* Visual Studio 2019 Preview 3 ou versions ultérieures

* Connaissance des outils en ligne de commande

## <a name="collect-performance-data"></a>Collecter des données de performances

Pour profiler une application à l’aide des outils CLI de diagnostics Visual Studio, l’outil de profilage et l’un des agents collecteurs sont attachés à un processus. Quand vous attachez l’outil de profilage, vous débutez une session de diagnostic qui capture et stocke des données de profilage jusqu’à l’arrêt de l’outil, après quoi ces données sont exportées dans un fichier *.diagsession*. Vous pouvez ensuite ouvrir ce fichier dans Visual Studio pour analyser les résultats.

1. Démarrez le Bloc-notes, puis ouvrez le Gestionnaire des tâches pour obtenir son ID de processus (PID). Dans le Gestionnaire des tâches, recherchez le PID sous l’onglet **Détails**.

1. Ouvrez une invite de commandes et passez au répertoire de l’exécutable de l’agent de collecte, qui se trouve généralement ici :

   ```<Visual Studio installation folder>\2019\Preview\Team Tools\DiagnosticsHub\Collector\```

1. Démarrez *VSDiagnostics.exe* en tapant la commande suivante :

   ```cmd
   VSDiagnostics.exe start <id> /attach:<pid> /loadConfig:<configFile>
   ```

   Les arguments qui doivent être inclus sont les suivants :

   * \<*id*> identifie la session de collecte. L’ID doit être un nombre compris entre 1 et 255.
   * \<*pid*> correspond au PID du processus à profiler, dans ce cas le PID identifié à l’étape 1.
   * \<*configFile*> correspond au fichier de configuration de l’agent de collecte que vous souhaitez lancer. Pour plus d’informations, consultez [Fichiers de configuration des agents](#config_file).

1. Redimensionnez le Bloc-notes ou tapez quelque chose pour que des informations de profilage intéressantes soient collectées.

1. Arrêtez la session de collecte et envoyez la sortie à un fichier en tapant la commande suivante :

   ```cmd
   VSDiagnostics.exe stop <id> /output:<path to file>
   ```

1. Accédez à la sortie du fichier de la commande précédente et ouvrez-la dans Visual Studio pour examiner les informations collectées.

## <a name="config_file"></a> Fichiers de configuration des agents

Les agents de collecte sont des composants interchangeables qui collectent différents types de données en fonction de ce que vous essayez de mesurer.

Pour des raisons pratiques, vous pouvez stocker ces informations dans un fichier de configuration d’agent. Le fichier de configuration est un fichier *.json* qui contient au minimum le nom du fichier *.dll* et son CLSID COM. Voici des exemples de fichiers de configuration que vous pouvez trouver dans le dossier suivant :

```<Visual Studio installation folder>\2019\Preview\Team Tools\DiagnosticsHub\Collector\AgentConfigs\```

* CpuUsage configurations (Base/High/Low), qui correspond aux données collectées pour l’outil de profilage [Utilisation de l’UC](../profiling/cpu-usage.md).
* DotNetObjectAlloc configurations (Base/Low), qui correspond aux données collectées pour l’[outil d’allocation d’objets .NET](https://devblogs.microsoft.com/visualstudio/visual-studio-2017-version-15-8-preview-3/#tooling).

Les configurations Base/Low/High font référence au taux d’échantillonnage. Par exemple, Low correspond à 100 échantillons/seconde et High à 4 000 échantillons/seconde.

Pour que l’outil *VSDiagnostics.exe* fonctionne avec un agent de collecte, il nécessite une DLL et un CLSID COM pour l’agent approprié. Ce dernier peut également avoir des options de configuration supplémentaires. Si vous utilisez un agent sans fichier de configuration, utilisez le format dans la commande suivante.

```cmd
VSDiagnostics.exe start <id> /attach:<pid> /loadAgent:<agentCLSID>;<agentName>[;<config>]
```

## <a name="permissions"></a>Autorisations

Pour profiler une application qui nécessite des autorisations élevées, vous devez le faire à partir d’une invite de commandes avec élévation de privilèges.
