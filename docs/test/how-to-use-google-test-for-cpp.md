---
title: Guide pratique pour utiliser Google Test pour C++
description: Utilisez Google Test pour créer des tests unitaires C++ dans Visual Studio.
ms.date: 05/06/2017
ms.topic: conceptual
ms.author: mblome
manager: markl
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 8e918878048eec7dae04b6d9269f664b9e99c567
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65226338"
---
# <a name="how-to-use-google-test-for-c-in-visual-studio"></a>Guide pratique pour utiliser Google Test pour C++ dans Visual Studio

Dans Visual Studio 2017 et ultérieur, Google Test est intégré dans l’IDE Visual Studio comme composant par défaut de la charge de travail **Développement Desktop en C++**. Pour vérifier qu’il est installé sur votre machine, ouvrez Visual Studio Installer et recherchez Google Test sous la liste des composants de charge de travail :

![Installation de Google Test](media/cpp-google-component.png)

::: moniker range="vs-2019"

## <a name="add-a-google-test-project-in-visual-studio-2019"></a>Ajouter un projet Google Test dans Visual Studio 2019

1. Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud de la solution et choisissez **Ajouter** > **Nouveau projet**.
2. Définissez **Langage** sur **C++** et tapez **test** dans la zone de recherche. Dans la liste des résultats, choisissez **Projet Google Test**.
3. Nommez le projet de test, puis cliquez sur **OK**.

![Nouveau projet Google Test](media/vs-2019/cpp-gtest-new-project-vs2019.png)

::: moniker-end

::: moniker range="vs-2017"

## <a name="add-a-google-test-project-in-visual-studio-2017"></a>Ajouter un projet Google Test dans Visual Studio 2017

1. Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud de la solution et choisissez **Ajouter** > **Nouveau projet**.
2. Dans le volet gauche, choisissez **Visual C++** > **Test**, puis **Projet Google Test** dans le volet central.
3. Nommez le projet de test, puis cliquez sur **OK**.

![Nouveau projet Google Test](media/cpp-gtest-new-project.png)

::: moniker-end

## <a name="configure-the-test-project"></a>Configurer le projet de test

Dans la boîte de dialogue **Configuration du projet de test** qui s’affiche, vous pouvez choisir le projet à tester. Quand vous choisissez un projet, Visual Studio ajoute une référence au projet sélectionné. Si vous ne choisissez aucun projet, vous devez ajouter manuellement des références au(x) projet(s) que vous voulez tester. Pour le choix entre les liaisons statiques et dynamiques pour les fichiers binaires Google Test, les considérations sont les mêmes que pour n’importe quel programme C++. Pour plus d’informations, consultez [DLL dans Visual C++](/cpp/build/dlls-in-visual-cpp).

 ![Configurer le projet Google Test](media/cpp-gtest-config.png)

## <a name="set-additional-options"></a>Définir des options supplémentaires

Dans le menu principal, choisissez **Outils** > **Options** > **Adaptateur de test pour Google Test** pour définir des options supplémentaires. Pour plus d’informations sur ces paramètres, consultez la documentation de Google Test.

 ![Paramètres du projet Google Test](media/cpp-gtest-settings.png)

## <a name="add-include-directives"></a>Ajouter des directives include

Dans le fichier *.cpp* de test, ajoutez les directives `#include` nécessaires pour rendre les types et les fonctions de votre programme visibles par le code de test. En règle générale, le programme est un niveau au-dessus dans l’arborescence des dossiers. Si vous tapez `#include "../"`, une fenêtre IntelliSense apparaît et vous permet de sélectionner le chemin complet du fichier d’en-tête.

![Ajouter des directives #include](media/cpp-gtest-includes.png)

## <a name="write-and-run-tests"></a>Écrire et exécuter des tests

Vous êtes maintenant prêt à écrire et à exécuter des tests Google. Pour plus d’informations sur les macros de test, consultez [Google Test Primer](https://github.com/google/googletest/blob/master/googletest/docs/primer.md). Pour plus d’informations sur la découverte, l’exécution et le regroupement de vos tests avec **l’Explorateur de tests**, consultez [Exécuter des tests unitaires avec l’Explorateur de tests](run-unit-tests-with-test-explorer.md).

## <a name="see-also"></a>Voir aussi

[Écrire des tests unitaires pour C/C++](writing-unit-tests-for-c-cpp.md)
