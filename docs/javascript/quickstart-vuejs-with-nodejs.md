---
title: 'Démarrage rapide : Créer une première application Vue.js'
description: Dans ce guide de démarrage rapide, vous allez créer une application Vue.js dans Visual Studio à l’aide des outils Node.js pour Visual Studio.
ms.custom: seodec18
ms.date: 09/24/2018
ms.topic: quickstart
ms.devlang: javascript
ms.assetid: b0e4ebed-1a01-41ef-aad1-4d8465ce5322
author: mikejo5000
ms.author: mikejo
manager: jillfra
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 28e86068b2255d1796363405c0231c1fb6bdd480
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65226496"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-vuejs-app"></a>Démarrage rapide : Utiliser Visual Studio pour créer une première application Vue.js

Dans cette présentation de 5-10 minutes de l’environnement de développement intégré (IDE) de Visual Studio, vous allez créer et exécuter une application web Vue.js simple.

> [!IMPORTANT]
> Le modèle Vue.js, disponible à partir de Visual Studio 2017 version 15.8, est nécessaire pour cet article.

## <a name="prerequisites"></a>Prérequis

* Au préalable, vous devez avoir installé Visual Studio et la charge de travail de développement Node.js.

    ::: moniker range=">=vs-2019"
    Si vous n’avez pas encore installé Visual Studio 2019, accédez à la page  [Téléchargements Visual Studio](https://visualstudio.microsoft.com/downloads/)  pour l’installer gratuitement.
    ::: moniker-end
    ::: moniker range="vs-2017"
    Si vous n’avez pas encore installé Visual Studio 2017, accédez à la page  [Téléchargements Visual Studio](https://visualstudio.microsoft.com/downloads/)  pour l’installer gratuitement.
    ::: moniker-end

    Si vous devez installer la charge de travail, mais que vous avez déjà installé Visual Studio, cliquez sur **Outils** > **Obtenir les outils et fonctionnalités...**, qui ouvre Visual Studio Installer. Choisissez la charge de travail **Développement Node.js**, puis choisissez **Modifier**.

    ![Charge de travail Node.js dans Visual Studio Installer](../ide/media/quickstart-nodejs-workload.png)

* Le runtime Node.js doit être installé.

    Si vous ne l’avez pas déjà fait, installez la version LTS à partir du site web [Node.js](https://nodejs.org/en/download/). En règle générale, Visual Studio détecte automatiquement le runtime Node.js installé. S’il ne détecte aucun runtime installé, vous pouvez configurer votre projet pour référencer le runtime installé dans la page de propriétés (après avoir créé un projet, cliquez avec le bouton droit sur le nœud de projet, puis choisissez **Propriétés**).

## <a name="create-a-project"></a>Créer un projet

Vous allez d’abord créer un projet d’application web Vue.js.

1. Si le runtime Node.js n’est pas déjà installé, installez la version LTS à partir du site web [Node.js](https://nodejs.org/en/download/).

    En règle générale, Visual Studio détecte automatiquement le runtime Node.js installé. S’il ne détecte aucun runtime installé, vous pouvez configurer votre projet pour référencer le runtime installé dans la page de propriétés (après avoir créé un projet, cliquez avec le bouton droit sur le nœud de projet, puis choisissez **Propriétés**).

1. Ouvrez Visual Studio.

1. Créer un nouveau projet.

    ::: moniker range=">=vs-2019"
    Appuyez sur **Échap** pour fermer la fenêtre de démarrage. Tapez **Ctrl+Q** pour ouvrir la zone de recherche, tapez **Basic Vue.js**, puis choisissez **Application web Vue.js de base** (JavaScript ou TypeScript). Dans la boîte de dialogue qui s’affiche, tapez le nom **basic-vuejs**, puis choisissez **Créer**.

    ![Modèle Vue.js](../javascript/media/vs-2019/vuejs-template.png)
    ::: moniker-end
    ::: moniker range="vs-2017"
    Dans la barre de menus supérieure, choisissez **Fichier** > **Nouveau** > **Projet**. Dans le volet gauche de la boîte de dialogue **Nouveau projet**, développez **JavaScript** ou **TypeScript**, puis choisissez **Node.js**. Dans le volet central, choisissez **Application web Vue.js de base**, tapez le nom **basic-vuejs**, puis choisissez **OK**.

    ![Modèle Vue.js](../javascript/media/vuejs-template.png)
    ::: moniker-end
    Si vous ne voyez pas le modèle de projet **Application web Vue.js de base**, vous devez ajouter la charge de travail **Développement Node.js**. Pour obtenir des instructions détaillées, consultez les [Prérequis](#prerequisites).

    Visual Studio crée le nouveau projet. Le nouveau projet s’ouvre dans l’Explorateur de solutions (volet droit).

1. Vérifiez la progression de l’installation des packages npm nécessaires pour l’application dans la fenêtre Sortie (volet inférieur).

1. Dans l’Explorateur de solutions, ouvrez le nœud **npm** et vérifiez que tous les packages npm répertoriés sont installés.

    S’il manque des packages (icône de point d’exclamation), vous pouvez cliquer avec le bouton droit sur le nœud **npm** et choisir **Installer les packages npm manquants**.

## <a name="explore-the-ide"></a>Explorer l’IDE

1. Observez **l’Explorateur de solutions** dans le volet droit.

     ![Solution Vue.js](../javascript/media/vuejs-solution.png)

   - Votre projet mis en gras, avec le nom que vous avez donné dans la boîte de dialogue **Nouveau projet**. Sur le disque, ce projet est représenté par un fichier *.njsproj* dans le dossier de votre projet.

   - Au niveau le plus élevé figure une solution, qui a par défaut le même nom que votre projet. Une solution, représentée par un fichier *.sln* sur le disque, est un conteneur pour un ou plusieurs projets connexes.

   - Le nœud **npm** montre tous les packages npm installés. Vous pouvez cliquer avec le bouton droit sur le nœud npm pour rechercher et installer des packages npm à l’aide d’une boîte de dialogue.

2. Si vous souhaitez installer des packages npm ou exécuter des commandes Node.js à partir d’une invite de commandes, cliquez avec le bouton droit sur le nœud du projet et choisissez **Ouvrir l’invite de commandes ici**.

## <a name="add-a-vue-file-to-the-project"></a>Ajouter un fichier .vue au projet

1. Dans l’Explorateur de solutions, cliquez avec le bouton droit sur n’importe quel dossier, par exemple le dossier *src/components*, puis choisissez **Ajouter** > **Nouvel élément**.

1. Sélectionnez **Composant monofichier Vue JavaScript** ou **Composant monofichier Vue TypeScript**, puis cliquez sur **Ajouter**.

    Visual Studio ajoute le nouveau fichier au projet.

## <a name="build-the-project"></a>Générer le projet

1. (Projet TypeScript uniquement) À partir de Visual Studio, choisissez **Générer** > **Nettoyer la solution**.

1. Ensuite, choisissez **Générer** > **Générer la solution** pour générer le projet. Consultez la fenêtre **Sortie** pour afficher les résultats de la génération, puis choisissez **Build** dans la liste **Afficher la sortie à partir de**.

    Le modèle de projet Vue.js utilise le script npm `build` en configurant un événement postbuild. Si vous souhaitez modifier ce paramètre, ouvrez le fichier projet (*\<nom_projet\>.njsproj*) à partir de l’Explorateur Windows et recherchez cette ligne de code :

    ```xml
    <PostBuildEvent>npm run build</PostBuildEvent>
    ```

## <a name="run-the-application"></a>Exécuter l'application

1. Appuyez sur **Ctrl**+**F5** ou (**Déboguer > Démarrer sans débogage**) pour exécuter l’application.

   Dans la console, un message signalant le *démarrage du serveur de développement* s’affiche.

   Ensuite, l’application s’ouvre dans un navigateur.

   ![Application Vue.js en cours d’exécution dans le navigateur](../javascript/media/vuejs-running-app.png)

1. Fermez le navigateur web.

Félicitations ! Vous avez terminé ce guide de démarrage rapide. Nous espérons que vous en avez appris un peu plus sur l’utilisation de l’IDE de Visual Studio avec Vue.js. Si vous souhaitez en savoir plus sur ses fonctionnalités, poursuivez avec l’un des tutoriels de la section **Tutoriels** dans la table des matières.

## <a name="next-steps"></a>Étapes suivantes

- Suivre le [tutoriel pour Node.js et Express](../nodejs/tutorial-nodejs.md)
- Suivre le [tutoriel pour Node.js et React](/visualstudio/javascript/tutorial-nodejs-with-react-and-jsx)
- [Déployer l’application sur Linux App Service](../javascript/publish-nodejs-app-azure.md)