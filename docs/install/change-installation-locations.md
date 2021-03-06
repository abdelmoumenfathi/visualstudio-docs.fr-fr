---
title: Sélectionner les emplacements d'installation
description: Découvrez comment réduire l’empreinte de l’installation de Visual Studio sur votre lecteur système en plaçant le cache de téléchargement, les composants partagés, les kits SDK et les outils sur d’autres lecteurs. Par exemple, déplacez des fichiers depuis le lecteur C vers le lecteur D.
ms.date: 03/30/2019
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- change installation locations for Visual Studio
- select an installation location for Visual Studio files
- move installation files to different drives
- use the D drive
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 651295d94a8125e26caa96b71ab438c62841ac10
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62974342"
---
# <a name="select-the-installation-locations-in-visual-studio"></a>Sélectionner les emplacements d’installation dans Visual Studio

::: moniker range="vs-2019"

Vous pouvez réduire l’empreinte de l’installation de Visual Studio sur votre lecteur système en changeant l’emplacement de certains de ses fichiers. Plus précisément, vous pouvez utiliser un autre emplacement pour le cache de téléchargement, les composants partagés, les SDK et les fichiers des outils.

::: moniker-end

::: moniker range="vs-2017"

**Nouveautés dans la version 15.7** : Vous pouvez réduire l’empreinte de l’installation de Visual Studio sur votre lecteur système en changeant l’emplacement de certains de ses fichiers. Plus précisément, vous pouvez utiliser un autre emplacement pour le cache de téléchargement, les composants partagés, les SDK et les fichiers des outils.

::: moniker-end

   > [!NOTE]
   > L’emplacement d’installation de certains outils et SDK est régi par des règles différentes. Ces outils et SDK sont toujours installés sur votre lecteur système, même si vous choisissez un autre emplacement.

Prêt à commencer ? Voici comment procéder.

::: moniker range="vs-2017"

1. Quand vous installez Visual Studio, choisissez l’onglet **Emplacements d’installation**.

   ![Visual Studio 2017 : Sélectionner l’emplacement d’installation](media/vs-installation-locations.png "Sélectionner l’emplacement d’installation.")

1. Dans la section **IDE Visual Studio**, acceptez la valeur par défaut. Visual Studio installe le noyau du produit et inclut les fichiers propres à cette version de Visual Studio.

   ![Section IDE Visual Studio de l’onglet Emplacements d’installation](media/vs-installation-locations-ide.png "Acceptez la valeur par défaut pour la section IDE Visual Studio de l’onglet Emplacement d’installation.")

   > [!TIP]
   > Si votre lecteur système est un disque SSD (Solid-State Drive), nous vous recommandons d’accepter l’emplacement par défaut sur votre lecteur système. Pourquoi ? Quand vous développez avec Visual Studio, vous lisez et écrivez un grand nombre de fichiers, ce qui augmente l’activité E/S du disque. Il est conseillé de choisir votre lecteur le plus rapide pour gérer la charge.

1. Dans la section **Cache de téléchargement**, indiquez si vous voulez conserver le cache de téléchargement, puis choisissez où stocker ses fichiers.

     ![Section Cache de téléchargement de l’onglet Emplacements d’installation](media/vs-installation-locations-cache.png "Choisissez s’il faut conserver le cache de téléchargement après l’installation, puis spécifiez le lecteur où stocker les fichiers.")

    1. Cochez ou décochez **Conserver le cache de téléchargement après l’installation**.

       Si vous décidez de ne pas conserver le cache de téléchargement, l’emplacement n’est utilisé que temporairement. Cette action n’affecte ni ne supprime les fichiers des installations précédentes.

    1. Spécifiez le lecteur où stocker les fichiers et manifestes d’installation du cache de téléchargement.

        Par exemple, si vous sélectionnez la charge de travail « Développement Desktop en C++ », la taille requise temporairement est de 1,58 Go sur votre lecteur système, qui est libérée dès que l’installation est terminée.

       > [!IMPORTANT]
       > L’emplacement est défini avec la première installation et vous ne pouvez plus le changer à partir de l’interface utilisateur du programme d’installation. À la place, vous devez [utiliser des paramètres de ligne de commande](use-command-line-parameters-to-install-visual-studio.md) pour déplacer le cache de téléchargement.

1. Dans la section **Composants partagés, outils et SDK**, spécifiez le lecteur où stocker les fichiers qui sont partagés par les installations côte à côte de Visual Studio. Les SDK et les outils sont également stockés dans ce répertoire.

   ![Section Composants partagés, outils et SDK de l’onglet Emplacements d’installation](media/vs-installation-locations-shared.png "Spécifiez l’emplacement où stocker les composants partagés, les outils et les SDK.")

::: moniker-end

::: moniker range="vs-2019"

1. Quand vous installez Visual Studio, choisissez l’onglet **Emplacements d’installation**.

   ![Visual Studio 2019 : Sélectionner l’emplacement d’installation](media/vs-2019/vs-installer-installation-locations.png "Sélectionner l’emplacement d’installation.")

1. Dans la section **IDE Visual Studio**, acceptez la valeur par défaut. Visual Studio installe le noyau du produit et inclut les fichiers propres à cette version de Visual Studio.

   > [!TIP]
   > Si votre lecteur système est un disque SSD (Solid-State Drive), nous vous recommandons d’accepter l’emplacement par défaut sur votre lecteur système. Pourquoi ? Quand vous développez avec Visual Studio, vous lisez et écrivez un grand nombre de fichiers, ce qui augmente l’activité E/S du disque. Il est conseillé de choisir votre lecteur le plus rapide pour gérer la charge.

1. Dans la section **Cache de téléchargement**, indiquez si vous voulez conserver le cache de téléchargement, puis choisissez où stocker ses fichiers.

    * Cochez ou décochez **Conserver le cache de téléchargement après l’installation**.

       Si vous décidez de ne pas conserver le cache de téléchargement, l’emplacement n’est utilisé que temporairement. Cette action n’affecte ni ne supprime les fichiers des installations précédentes.

    * Spécifiez le lecteur où stocker les fichiers et manifestes d’installation du cache de téléchargement.

        Par exemple, si vous sélectionnez la charge de travail « Développement Desktop en C++ », la taille requise temporairement est de 1,58 Go sur votre lecteur système, qui est libérée dès que l’installation est terminée.

       > [!IMPORTANT]
       > L’emplacement est défini avec la première installation et vous ne pouvez plus le changer à partir de l’interface utilisateur du programme d’installation. À la place, vous devez [utiliser des paramètres de ligne de commande](use-command-line-parameters-to-install-visual-studio.md) pour déplacer le cache de téléchargement.

1. Dans la section **Composants partagés, outils et SDK**, notez qu’il utilise le même lecteur que celui que vous avez choisi dans la section « Cache de téléchargement ». Le répertoire \Microsoft\VisualStudio\Shared est l’emplacement auquel Visual Studio stocke les fichiers qui sont partagés par les installations côte à côte de Visual Studio. Les SDK et les outils sont également stockés dans ce répertoire.

::: moniker-end

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Voir aussi

* [Installer Visual Studio](install-visual-studio.md)
* [Mettre à jour Visual Studio](update-visual-studio.md)
* [Modifier Visual Studio](update-visual-studio.md)
* [Désinstaller Visual Studio](uninstall-visual-studio.md)
