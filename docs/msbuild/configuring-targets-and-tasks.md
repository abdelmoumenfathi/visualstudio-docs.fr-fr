---
title: Configuration des cibles et des tâches | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 9aabe67a-1720-4bbf-80d3-822b3ccf75c0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de6f1168b55af2337dfb235d05c9c8376b2614c1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778237"
---
# <a name="configure-targets-and-tasks"></a>Configurer les cibles et les tâches
Vous pouvez configurer des cibles et des tâches MSBuild pour qu’elles s’exécutent hors processus avec MSBuild. Vous pouvez ainsi cibler des contextes différents de celui dans lequel vous vous trouvez. Par exemple, vous pouvez cibler une application .NET Framework 2.0 32 bits alors que l’ordinateur de développement s’exécute sur un système d’exploitation 64 bits avec le .NET Framework 4.5. Vous pouvez également cibler des ordinateurs qui exécutent le .NET Framework 4 ou version antérieure. La combinaison d’un système 32 et 64 bits et de la version spécifique du .NET Framework est appelée *contexte cible*.

## <a name="installation"></a>Installation
 Les versions 4.5 et 4.5.1 du .NET Framework remplacent le common language runtime (CLR), les cibles, les tâches et les outils du .NET Framework 4 sans les renommer. .NET Framework 4.5.1 est installé avec [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)].

 Si vous souhaitez installer MSBuild séparément de Visual Studio, vous pouvez télécharger le package d’installation à partir de la page de [téléchargement de MSBuild](http://go.microsoft.com/fwlink/?LinkId=309745). Vous devez également installer les versions du .NET Framework que vous souhaitez utiliser.

## <a name="targets-and-tasks"></a>Cibles et tâches
 MSBuild exécute certaines des tâches de génération hors processus pour cibler un ensemble plus important de contextes.  Par exemple, un MSBuild 32 bits peut exécuter une tâche de génération dans un processus 64 bits pour cibler un ordinateur 64 bits. Pour cela, utilisez les arguments `UsingTask` et les paramètres `Task`. Les cibles installées par le .NET Framework 4.5 définissent ces paramètres et ces arguments, et aucune modification n’est nécessaire pour générer des applications adaptées aux différents contextes cible.

 Si vous souhaitez créer votre propre contexte cible, vous devez définir correctement ces paramètres et ces arguments. Pour obtenir des exemples, examinez les fichiers *Microsoft.Common.targets* et *Microsoft.Common.Tasks* de .NET Framework 4.5.  Pour plus d’informations sur la façon de créer une tâche personnalisée pouvant fonctionner avec plusieurs contextes cibles, ou sur la façon de modifier des tâches existantes, consultez [Guide pratique pour configurer les cibles et les tâches](../msbuild/how-to-configure-targets-and-tasks.md).

## <a name="see-also"></a>Voir aussi
- [Multiciblage](../msbuild/msbuild-multitargeting-overview.md)