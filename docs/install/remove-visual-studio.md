---
title: Supprimer Visual Studio
titleSuffix: ''
description: Découvrez comment supprimer complètement Visual Studio de votre ordinateur, étape par étape.
ms.date: 03/30/2019
ms.custom: seodec18
ms.topic: conceptual
f1_keywords:
- uninstall
- uninstall Visual Studio
- remove
- remove Visual Studio
- cleanup
- cleanup Visual Studio
- clean up
- clean up Visual Studio
ms.assetid: 9c81a777-9c95-4934-b517-c60c6dc78799
author: heaths
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: e363065d96169660817a548fb97d39f09cf679c9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62810388"
---
# <a name="remove-visual-studio"></a>Supprimer Visual Studio

Si vous rencontrez une erreur grave et ne parvenez pas à réparer ou à désinstaller Visual Studio, vous pouvez exécuter l’outil `InstallCleanup.exe` pour supprimer les fichiers d’installation et les informations produit de toutes les instances installées de Visual Studio 2017 ou 2019. Cet outil ne doit être exécuté qu’en dernier recours, lorsque la réparation ou la désinstallation échouent. En effet, l’outil peut désinstaller des fonctionnalités d’autres installations de Visual Studio ou d’autres produits qui doivent alors aussi être réparés.

Dans les instructions suivantes, vous pouvez exécuter l’outil avec différents commutateurs de ligne de commande au comportement suivant :

| Basculer | Comportement |
| ------ | -------- |
| `-i`   | Il s’agit du commutateur par défaut si aucun autre commutateur n’est passé. Il supprime uniquement le répertoire d’installation principal et les informations produit. Ce comportement est préférable si vous envisagez de réinstaller la même version après avoir exécuté l’outil `InstallCleanup.exe`. |
| `-f`   | La spécification de ce commutateur supprime le répertoire d’installation principal, les informations produit et la plupart des autres fonctionnalités installées en dehors du répertoire d’installation, et qui peuvent être partagées avec d’autres installations de Visual Studio ou d’autres produits. Ce comportement est préférable si vous prévoyez de supprimer Visual Studio et de ne pas le réinstaller. |

1. Fermez le programme d’installation de Visual Studio.
2. Ouvrez une invite de commandes administrateur. Pour ouvrir une invite de commandes administrateur, suivez les étapes ci-dessous :
   * Tapez **cmd** dans la zone « Tapez ici pour effectuer une recherche ».
   * Cliquez avec le bouton droit de la souris sur **Invite de commande**, puis cliquez sur **Exécuter en tant qu'administrateur**.
3. Tapez le chemin complet de l’utilitaire `InstallCleanup.exe` et passez le commutateur de ligne de commande de votre choix. Par défaut, le chemin de l’utilitaire est le suivant :

   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```

Si vous ne trouvez pas `InstallCleanup.exe` dans le répertoire Visual Studio Installer (qui est toujours situé ici : `%ProgramFiles(x86)%\Microsoft Visual Studio`), suivez les instructions de [désinstallation de Visual Studio](install-visual-studio.md), et lorsque l’écran de sélection de la charge de travail s’affiche, fermez la fenêtre, puis suivez de nouveau les étapes précédentes.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Voir aussi

* [Installer Visual Studio](install-visual-studio.md)
* [Mettre à jour Visual Studio](update-visual-studio.md)
* [Modifier Visual Studio](modify-visual-studio.md)
* [Désinstaller Visual Studio](uninstall-visual-studio.md)
