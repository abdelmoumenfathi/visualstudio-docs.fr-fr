---
title: Collecte des données de temporisation détaillées d’une application web ASP.NET en utilisant la méthode d’instrumentation de Profiler à partir de la ligne de commande | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling tools,instrumentation method
- instrumentation profiling method
ms.assetid: 29f2fc55-aaf7-4e18-a672-8815455fba73
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: 79e8ad7842070d13941ad921ccb25ba502209eb0
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63405955"
---
# <a name="collect-detailed-timing-data-for-an-aspnet-web-application-using-the-profiler-instrumentation-method-from-the-command-line"></a>Collecter des données temporelles détaillées d’une application web ASP.NET en utilisant la méthode d’instrumentation du profileur à partir de la ligne de commande
Cette section décrit les procédures et les options permettant de collecter des données de performances détaillées pour une application web [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] à l’aide de l’outil en ligne de commande **VSPerfCmd** et de la méthode d’instrumentation.

> [!NOTE]
> L’outil **VSPerfCmd** vous permet d’accéder à l’intégralité des fonctionnalités des Outils de profilage, notamment la mise en suspens et la reprise du profilage, ainsi que la collecte de données supplémentaires auprès du processeur et des compteurs de performances Windows. Vous pouvez également utiliser l’outil en ligne de commande **VSPerfASPNETCmd** quand vous n’avez pas besoin de ces fonctionnalités. Par rapport à l’outil en ligne de commande [VSPerfCmd](../profiling/vsperfcmd.md), cet outil ne nécessite pas de définition de variables d’environnement, ni de redémarrage de l’ordinateur. Pour plus d’informations, consultez [Profilage de site web rapide avec VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).

## <a name="common-tasks"></a>Tâches courantes

|Tâche|Contenu associé|
|----------|---------------------|
|**Profiler des fichiers binaires compilés statiquement**|-   [Guide pratique pour instrumenter une application ASP.NET compilée statiquement et collecter des données de temporisation détaillées](../profiling/how-to-instrument-statically-compiled-aspnet-and-collect-detailed-timing-data.md)|
|**Profiler des fichiers binaires compilés dynamiquement**|-   [Guide pratique pour instrumenter une application ASP.NET compilée dynamiquement et collecter des données de temporisation détaillées](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-app-and-collect-timing-data.md)|

## <a name="related-tasks"></a>Tâches connexes

### <a name="profile-aspnet-web-applications"></a>Profiler des applications web ASP.NET

|Tâche|Contenu associé|
|----------|---------------------|
|**Profiler à l’aide de la méthode d’échantillonnage**|-   [Collecter des statistiques d’applications en utilisant l’échantillonnage](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|
|**Profiler l’allocation de mémoire et le garbage collection**|-   [Collecter des données de mémoire](../profiling/collecting-memory-data-from-an-aspnet-web-application.md)|
|**Profiler le conflit des ressources et l’activité des threads**|-   [Collecter des données concurrentielles](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|

### <a name="profile-by-using-the-instrumentation-method"></a>Profiler avec la méthode d’instrumentation

|Tâche|Contenu associé|
|----------|---------------------|
|**Profiler des applications autonomes (clientes)**|-   [Collecter les données temporelles détaillées à l’aide de l’instrumentation](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application.md)|
|**Profiler des services**|-   [Collecter les données temporelles détaillées à l’aide de l’instrumentation](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method.md)|

### <a name="analyze-instrumentation-data-views-and-reports"></a>Analyser des vues et des rapports de données d’instrumentation
- [Vues de données de la méthode d'instrumentation](../profiling/instrumentation-method-data-views.md)