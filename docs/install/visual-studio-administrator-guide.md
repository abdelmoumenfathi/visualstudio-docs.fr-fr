---
title: Guide de l’administrateur Visual Studio
titleSuffix: ''
description: En savoir plus sur le déploiement de Visual Studio dans un environnement d’entreprise.
ms.date: 05/22/2019
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: b89f8415d34a4facaca694db8507c911d279bf8f
ms.sourcegitcommit: 92a04c57ac0a49f304fa2ea5043436f30068c3cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/21/2019
ms.locfileid: "65976120"
---
# <a name="visual-studio-administrator-guide"></a>Guide de l’administrateur Visual Studio

Dans les environnements d’entreprise, les administrateurs système déploient généralement les installations pour les utilisateurs finaux à partir d’un partage réseau ou à l’aide d’un logiciel de gestion de systèmes. Nous avons conçu le moteur d’installation de Visual Studio pour prendre en charge le déploiement d’entreprise en offrant aux administrateurs système la possibilité de créer un emplacement d’installation réseau pour préconfigurer les paramètres d’installation par défaut, déployer des clés de produit pendant le processus d’installation et gérer les mises à jour de produit après un déploiement réussi.

Ce guide de l’administrateur fournit des conseils basés sur des scénarios pour un déploiement d’entreprise dans les environnements réseau.

## <a name="before-you-begin"></a>Avant de commencer

Avant de déployer Visual Studio à l’échelle de votre organisation, vous avez quelques décisions à prendre et quelques tâches à effectuer :

::: moniker range="vs-2019"

* Vérifiez que chaque ordinateur cible présente la [configuration minimale requise pour l’installation](/visualstudio/releases/2019/system-requirements/).

* Déterminez vos besoins de maintenance.

  Si votre entreprise a besoin de rester plus longtemps sur un ensemble de fonctionnalités, mais qu’elle souhaite quand même bénéficier de mises à jour de maintenance régulières, envisagez d’utiliser un planning de référence pour la maintenance. Pour plus d’informations, consultez la section ***Options de support pour les clients Enterprise et Professional*** de la page [Cycle de vie et maintenance des produits Visual Studio](/visualstudio/releases/2019/servicing#support-options-for-enterprise-and-professional-customers).

  Si vous envisagez d’appliquer des mises à jour de maintenance parallèlement aux mises à jour cumulatives des fonctionnalités, vous pouvez choisir les derniers composants.

* Choisissez le modèle de mise à jour.

  D’où doivent provenir les mises à jour pour les machines clientes ? Concrètement, déterminez si vous voulez obtenir les mises à jour d’Internet ou d’un partage local à l’échelle de l’entreprise. Ensuite, si vous choisissez d’utiliser un partage local, décidez si chaque utilisateur doit pouvoir mettre à jour son propre client ou si vous voulez qu’un administrateur mette à jour les clients par programmation.

* Déterminez les [charges de travail et les composants](workload-and-component-ids.md?view=vs-2019) dont a besoin votre entreprise.

* Décidez s’il convient d’utiliser un [fichier réponse](automated-installation-with-response-file.md?view=vs-2019) (qui simplifie la gestion des détails dans le fichier de script).

* Déterminez si vous souhaitez activer la stratégie de groupe et si vous voulez configurer Visual Studio pour désactiver les commentaires du client sur les ordinateurs individuels.

::: moniker-end

::: moniker range="vs-2017"

* Vérifiez que chaque ordinateur cible présente la [configuration minimale requise pour l’installation](/visualstudio/productinfo/vs2017-system-requirements-vs/).

* Déterminez vos besoins de maintenance.

  Si votre entreprise a besoin de rester plus longtemps sur un ensemble de fonctionnalités, mais qu’elle souhaite quand même bénéficier de mises à jour de maintenance régulières, envisagez d’utiliser un planning de référence pour la maintenance. Pour plus d’informations, consultez la section ***Prise en charge des versions antérieures de Visual Studio*** de la page [Cycle de vie et maintenance des produits Visual Studio](/visualstudio/releases/2019/servicing#support-for-older-versions-of-visual-studio).

  Si vous envisagez d’appliquer des mises à jour de maintenance parallèlement aux mises à jour cumulatives des fonctionnalités, vous pouvez choisir les derniers composants.

* Choisissez le modèle de mise à jour.

  D’où doivent provenir les mises à jour pour les machines clientes ? Concrètement, déterminez si vous voulez obtenir les mises à jour d’Internet ou d’un partage local à l’échelle de l’entreprise. Ensuite, si vous choisissez d’utiliser un partage local, décidez si chaque utilisateur doit pouvoir mettre à jour son propre client ou si vous voulez qu’un administrateur mette à jour les clients par programmation.

* Déterminez les [charges de travail et les composants](workload-and-component-ids.md?view=vs-2017) dont a besoin votre entreprise.

* Décidez s’il convient d’utiliser un [fichier réponse](automated-installation-with-response-file.md?view=vs-2017) (qui simplifie la gestion des détails dans le fichier de script).

* Déterminez si vous souhaitez activer la stratégie de groupe et si vous voulez configurer Visual Studio pour désactiver les commentaires du client sur les ordinateurs individuels.

::: moniker-end

::: moniker range="vs-2019"

## <a name="step-1---download-visual-studio-product-files"></a>Étape 1 – Télécharger les fichiers du produit Visual Studio

* [Sélectionnez les charges de travail et les composants](workload-and-component-ids.md?view=vs-2019) que vous souhaitez installer.

* [Créez un partage réseau pour les fichiers du produit Visual Studio](create-a-network-installation-of-visual-studio.md?view=vs-2019).

## <a name="step-2---build-an-installation-script"></a>Étape 2 – Créer un script d’installation

* Créez un script d’installation qui utilise des [paramètres de ligne de commande](use-command-line-parameters-to-install-visual-studio.md?view=vs-2019) pour contrôler l’installation.

  >[!NOTE]
  > Vous pouvez simplifier les scripts à l’aide d’un [fichier réponse](automated-installation-with-response-file.md?view=vs-2019). Veillez à créer un fichier réponse qui contient votre option d’installation par défaut.

* (Facultatif) [Appliquez une clé de produit de licence en volume](automatically-apply-product-keys-when-deploying-visual-studio.md?view=vs-2019) dans le script d’installation de sorte que les utilisateurs n’aient pas besoin d’activer le logiciel séparément.

* (Facultatif) Mettez à jour la topologie réseau pour [contrôler à quel moment les mises à jour du produit sont remises aux utilisateurs finaux et d’où elles proviennent](controlling-updates-to-visual-studio-deployments.md?view=vs-2019).

* (Facultatif) Définissez les stratégies de Registre qui ont une incidence sur le déploiement de Visual Studio comme l’emplacement d’installation de certains packages partagés avec d’autres versions ou instances, l’[emplacement de mise en cache des packages](set-defaults-for-enterprise-deployments.md?view=vs-2019) ou [si les packages sont mis en cache](disable-or-move-the-package-cache.md?view=vs-2019).

* (Facultatif) Définissez la stratégie de groupe. Vous pouvez aussi [configurer Visual Studio pour désactiver les commentaires du client](../ide/visual-studio-experience-improvement-program.md) sur les ordinateurs individuels.

## <a name="step-3---deploy"></a>Étape 3 – Déployer

* Utilisez la technologie de déploiement de votre choix pour exécuter votre script sur vos stations de travail de développement cibles.

## <a name="step-4---deploy-updates"></a>Étape 4 – Déployer les mises à jour

* [Actualiser votre emplacement réseau avec les dernières mises à jour](update-a-network-installation-of-visual-studio.md?view=vs-2019) de Visual Studio en exécutant régulièrement la commande utilisée à l’étape 1 pour ajouter des composants mis à jour.

  Vous pouvez mettre à jour Visual Studio à l’aide d’un script de mise à jour. Pour ce faire, utilisez le paramètre de ligne de commande [`update`](use-command-line-parameters-to-install-visual-studio.md?view=vs-2019).

## <a name="step-5---optional-use-visual-studio-tools"></a>Étape 5 – (Facultatif) Utiliser les outils Visual Studio

Plusieurs outils sont disponibles pour vous aider à [détecter et à gérer les instances de Visual Studio installées](tools-for-managing-visual-studio-instances.md?view=vs-2019) sur les ordinateurs clients.

::: moniker-end

::: moniker range="vs-2017"

## <a name="step-1---download-visual-studio-product-files"></a>Étape 1 – Télécharger les fichiers du produit Visual Studio

* [Sélectionnez les charges de travail et les composants](workload-and-component-ids.md?view=vs-2017) que vous souhaitez installer.

* [Créez un partage réseau pour les fichiers du produit Visual Studio](create-a-network-installation-of-visual-studio.md?view=vs-2017).

## <a name="step-2---build-an-installation-script"></a>Étape 2 – Créer un script d’installation

* Créez un script d’installation qui utilise des [paramètres de ligne de commande](use-command-line-parameters-to-install-visual-studio.md?view=vs-2017) pour contrôler l’installation.

  >[!NOTE]
  > Vous pouvez simplifier les scripts à l’aide d’un [fichier réponse](automated-installation-with-response-file.md?view=vs-2017). Veillez à créer un fichier réponse qui contient votre option d’installation par défaut.

* (Facultatif) [Appliquez une clé de produit de licence en volume](automatically-apply-product-keys-when-deploying-visual-studio.md?view=vs-2017) dans le script d’installation de sorte que les utilisateurs n’aient pas besoin d’activer le logiciel séparément.

* (Facultatif) Mettez à jour la topologie réseau pour [contrôler à quel moment les mises à jour du produit sont remises aux utilisateurs finaux et d’où elles proviennent](controlling-updates-to-visual-studio-deployments.md?view=vs-2017).

* (Facultatif) Définissez les stratégies de Registre qui ont une incidence sur le déploiement de Visual Studio comme l’emplacement d’installation de certains packages partagés avec d’autres versions ou instances, l’[emplacement de la mise en cache des packages](set-defaults-for-enterprise-deployments.md?view=vs-2019) ou [si les packages sont mis en cache](disable-or-move-the-package-cache.md?view=vs-2017).

* (Facultatif) Définissez la stratégie de groupe. Vous pouvez aussi [configurer Visual Studio pour désactiver les commentaires du client](../ide/visual-studio-experience-improvement-program.md) sur les ordinateurs individuels.

## <a name="step-3---deploy"></a>Étape 3 – Déployer

* Utilisez la technologie de déploiement de votre choix pour exécuter votre script sur vos stations de travail de développement cibles.

## <a name="step-4---deploy-updates"></a>Étape 4 – Déployer les mises à jour

* [Actualiser votre emplacement réseau avec les dernières mises à jour](update-a-network-installation-of-visual-studio.md?view=vs-2017) de Visual Studio en exécutant régulièrement la commande utilisée à l’étape 1 pour ajouter des composants mis à jour.

  Vous pouvez mettre à jour Visual Studio à l’aide d’un script de mise à jour. Pour ce faire, utilisez le paramètre de ligne de commande [`update`](use-command-line-parameters-to-install-visual-studio.md?view=vs-2019).

## <a name="step-5---optional-use-visual-studio-tools"></a>Étape 5 – (Facultatif) Utiliser les outils Visual Studio

Plusieurs outils sont disponibles pour vous aider à [détecter et à gérer les instances de Visual Studio installées](tools-for-managing-visual-studio-instances.md?view=vs-2017) sur les ordinateurs clients.

::: moniker-end

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Voir aussi

* [Exemples de paramètres de ligne de commande](command-line-parameter-examples.md)
* [Installer les certificats nécessaires à l’installation hors connexion de Visual Studio](install-certificates-for-visual-studio-offline.md)
* [Importer ou exporter des configurations d’installation](import-export-installation-configurations.md)
* [Archives d’installation de Visual Studio](https://devblogs.microsoft.com/setup/tag/vs2017/)
* [Cycle de vie et maintenance des produits Visual Studio](/visualstudio/releases/2019/servicing/)
