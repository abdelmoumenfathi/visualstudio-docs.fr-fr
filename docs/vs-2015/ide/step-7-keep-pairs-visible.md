---
title: 'Étape 7 : Garder les paires visibles | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 42e1d08c-7b2e-4efd-9f47-85d6206afe35
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4f0c0b7b3e1edb367db6a49987a67e8a6dfdc17c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60112050"
---
# <a name="step-7-keep-pairs-visible"></a>Étape 7 : Garder les paires visibles
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Le jeu fonctionne correctement tant que le joueur se contente de choisir des paires d'icônes qui ne correspondent pas. Voyons ce qui doit se produire lorsque le joueur choisit une paire d'icônes identiques. Au lieu de faire disparaître les icônes en activant le minuteur (à l'aide de la méthode `Start()`), le jeu doit se réinitialiser pour arrêter le suivi de tous les contrôles Label à l'aide des variables de référence `firstClicked` et `secondClicked`, sans réinitialiser les couleurs des deux contrôles Label choisis.  
  
### <a name="to-keep-pairs-visible"></a>Pour garder des paires visibles  
  
1. Ajoutez l'instruction `if` suivante à la méthode de gestionnaire d'événements `label_Click()`, vers la fin du code, juste au-dessus de l'instruction où vous démarrez le minuteur. Examinez attentivement le code lorsque vous l'ajoutez au programme. Analysez son fonctionnement.  
  
     [!code-csharp[VbExpressTutorial4Step7#9](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step7/cs/form1.cs#9)]
     [!code-vb[VbExpressTutorial4Step7#9](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step7/vb/form1.vb#9)]  
  
     La première ligne de l'instruction `if` que vous venez d'ajouter vérifie si l'icône du premier contrôle Label choisi par le joueur est la même que l'icône du deuxième contrôle Label. Si les icônes sont identiques, le programme exécute les trois instructions entre les accolades en C# ou les trois instructions dans l'instruction `if` en Visual Basic. Les deux premières instructions réinitialisent les variables de référence `firstClicked` et `secondClicked` pour arrêter le suivi des différents contrôles Label. (Vous pouvez identifier ces deux instructions dans le gestionnaire d'événements Tick de la minuterie.) La troisième instruction est une instruction `return`, qui indique au programme d'ignorer le reste des instructions dans la méthode et de ne pas les exécuter.  
  
     Si vous programmez en Visual C#, vous aurez éventuellement remarqué qu'une partie du code utilise un seul signe égal (`=`), alors que d'autres instructions en utilisent deux (`==`). Examinez pourquoi `=` est utilisé dans certains cas et `==` dans d'autres.  
  
     Cet exemple montre bien la différence entre les deux cas. Examinez attentivement le code entre parenthèses dans l'instruction `if`.  
  
    ```vb  
    firstClicked.Text = secondClicked.Text  
    ```  
  
    ```csharp  
    firstClicked.Text == secondClicked.Text  
    ```  
  
     Analysez ensuite attentivement la première instruction dans le bloc de code après l'instruction `if`.  
  
    ```vb  
    firstClicked = Nothing  
    ```  
  
    ```csharp  
    firstClicked = null;  
    ```  
  
     La première de ces deux instructions vérifie si deux icônes sont identiques. Étant donné que deux valeurs sont comparées, le programme Visual C# utilise l'opérateur d'égalité `==`. En fait, la deuxième instruction modifie la valeur (appelée *assignation*) en affectant la valeur `null` à la variable de référence `firstClicked` pour la réinitialiser. C'est la raison pour laquelle elle utilise plutôt l'opérateur d'assignation `=`. Visual C# utilise `=` pour définir des valeurs et `==` pour les comparer. Le langage Visual Basic utilise `=` pour l'affectation et la comparaison des variables.  
  
2. Enregistrez et exécutez le programme, puis commencez à choisir des icônes sur le formulaire. Si vous choisissez une paire qui ne correspond pas, l'événement Tick du minuteur se déclenche et les deux icônes disparaissent. Si vous choisissez une paire d'icônes identiques, la nouvelle instruction `if` s'exécute et l'instruction return indique à la méthode d'ignorer le code qui démarre le minuteur. De cette façon, les icônes restent visibles, comme le montre la figure ci-dessous.  
  
     ![Jeu créé dans ce didacticiel](../ide/media/express-finishedgame.png "Express_FinishedGame")  
Jeu de combinaisons avec des paires d'icônes visibles  
  
### <a name="to-continue-or-review"></a>Pour continuer ou examiner  
  
- Pour passer à l’étape suivante du tutoriel, consultez [Étape 8 : Ajoutez une méthode pour vérifier si le joueur a gagné](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md).  
  
- Pour revenir à l’étape précédente du tutoriel, consultez [Étape 6 : Ajouter une minuterie](../ide/step-6-add-a-timer.md).
