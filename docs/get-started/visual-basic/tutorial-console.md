---
title: 'Tutoriel : Bien démarrer avec Visual Basic'
description: Découvrez comment créer des applications console Visual Basic dans Visual Studio, étape par étape.
ms.custom: seodec18, get-started
ms.date: 03/23/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: tutorial
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: 234a2d1070a39c0f9d9dbf5b0ae706b02b660abf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62972475"
---
# <a name="tutorial-get-started-with-visual-basic-in-visual-studio"></a>Tutoriel : Bien démarrer avec Visual Basic dans Visual Studio

Dans ce tutoriel pour Visual Basic (VB), vous allez utiliser Visual Studio afin de créer et d’exécuter différentes applications console tout en explorant certaines fonctionnalités de l’[IDE (environnement de développement intégré) Visual Studio](visual-studio-ide.md).

::: moniker range="vs-2017"

Si vous n’avez pas encore installé Visual Studio, accédez à la page [Téléchargements Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) pour l’installer gratuitement.

::: moniker-end

::: moniker range="vs-2019"

Si vous n’avez pas encore installé Visual Studio, accédez à la page [Téléchargements Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) pour l’installer gratuitement.

::: moniker-end

## <a name="create-a-project"></a>Créer un projet

Tout d’abord, nous allons créer un projet d’application Visual Basic. Le type de projet inclut tous les fichiers de modèle dont vous aurez besoin au départ.

::: moniker range="vs-2017"

1. Ouvrez Visual Studio 2017.

2. Dans la barre de menus supérieure, choisissez **Fichier** > **Nouveau** > **Projet**.

3. Dans la boîte de dialogue **Nouveau projet**, dans le volet gauche, développez **Visual Basic**, puis choisissez **.NET Core**. Dans le volet central, choisissez **Application console (.NET Core)**. Ensuite, nommez le fichier *HelloWorld*.

   ![Modèle de projet d’application console (.NET Core) dans la boîte de dialogue Nouveau projet dans l’IDE de Visual Studio](media/new-project-vb-dotnetcore-whatisyourname-console-app.png)

### <a name="add-a-workload-optional"></a>Ajouter une charge de travail (facultatif)

Si vous ne voyez pas le modèle de projet **Application console (.NET Core)**, vous pouvez l’obtenir en ajoutant la charge de travail **Développement multiplateforme .NET Core**. Vous pouvez ajouter cette charge de travail de l’une des deux manières suivantes, en fonction des mises à jour de Visual Studio 2017 qui sont installées sur votre ordinateur.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Option 1 : Utiliser la boîte de dialogue Nouveau projet

1. Cliquez sur le lien **Ouvrir Visual Studio Installer** dans le volet gauche de la boîte de dialogue **Nouveau projet**.

   ![Cliquer sur le lien Ouvrir Visual Studio Installer dans la boîte de dialogue Nouveau projet](../media/vs-open-visual-studio-installer-generic.png)

1. Visual Studio Installer est lancé. Choisissez la charge de travail **Développement multiplateforme .NET Core**, puis choisissez **Modifier**.

   ![Charge de travail Développement multiplateforme .Net Core dans Visual Studio Installer](../media/tutorial-aspnet-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>Option 2 : Utiliser la barre de menus Outils

1. Quittez la boîte de dialogue **Nouveau projet** puis, dans la barre de menus supérieure, choisissez **Outils** > **Obtenir les outils et fonctionnalités**.

1. Visual Studio Installer est lancé. Choisissez la charge de travail **Développement multiplateforme .NET Core**, puis choisissez **Modifier**.

::: moniker-end

::: moniker range="vs-2019"

> [!NOTE]
> Certaines des captures d’écran de ce tutoriel utilisent le thème foncé. Si vous n’utilisez pas le thème foncé, mais que vous aimeriez l’utiliser, consultez la page [Personnaliser l’éditeur et l’IDE de Visual Studio](../../ide/quickstart-personalize-the-ide.md) pour savoir comment faire.

1. Ouvrez Visual Studio 2019.

1. Dans la fenêtre de démarrage, choisissez **Créer un projet**.

   ![Afficher la fenêtre « Créer un projet »](../../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. Dans la fenêtre **Créer un projet**, entrez ou tapez *console* dans la zone de recherche. Ensuite, choisissez **Visual Basic** dans la liste des langages, puis choisissez **Windows** dans la liste des plateformes. 

   Après avoir appliqué les filtres de langage et de plateforme, choisissez le modèle **Application console (.NET Core)**, puis choisissez **Suivant**.

   ![Choisir le modèle Visual Basic pour l’application console (.NET Framework)](./media/vs-2019/vb-create-new-project-search-console-net-core-filtered.png)

   > [!NOTE]
   > Si vous ne voyez pas le modèle **Application console (.NET Core)**, vous pouvez l’installer à partir de la fenêtre **Créer un projet**. Dans le **Vous ne trouvez pas ce que vous cherchez ?**, choisissez le lien **Installer plus d’outils et de fonctionnalités**.
   >
   > ![Le lien « Installer plus d’outils et de fonctionnalités » du message « Vous ne trouvez pas ce que vous cherchez ? » dans la fenêtre « Créer un projet »](../../get-started/media/vs-2019/not-finding-what-looking-for.png) 
   > 
   > Ensuite, dans Visual Studio Installer, choisissez la charge de travail **Développement multiplateforme .NET Core**.
   >
   > ![Charge de travail Développement multiplateforme .Net Core dans Visual Studio Installer](../../get-started/media/dot-net-core-xplat-dev-workload.png)
   >
   > Après cela, choisissez le bouton **Modifier** dans Visual Studio Installer. Vous pouvez être invité à enregistrer votre travail ; le cas échéant, faites-le. Ensuite, choisissez **Continuer** pour installer la charge de travail. Ensuite, revenez à l’étape 2 de cette procédure « [Créer un projet](#create-a-project) ».

1. Dans la fenêtre **Configurer votre nouveau projet**, tapez ou entrez *WhatIsYourName* dans la zone **Nom du projet**. Choisissez ensuite **Créer**.

   ![Dans la fenêtre « Configurer votre nouveau projet », nommez votre projet « WhatIsYourName »](./media/vs-2019/vb-name-your-project-whatname.png)

   Visual Studio ouvre votre nouveau projet.

::: moniker-end

## <a name="create-a-what-is-your-name-application"></a>Créer une application « Quel est votre nom »

Nous allons créer une application qui vous demande votre nom et l’affiche, ainsi que la date et l’heure. Voici comment :

 ::: moniker range="vs-2017"

1. S’il n’est pas déjà ouvert, ouvrez votre projet *WhatIsYourName*.

1. Entrez le code Visual Basic suivant juste après le crochet ouvrant qui suit la ligne `Sub Main(args As String())` et avant la ligne `End Sub` :

     ```vb
     Console.WriteLine(vbCrLf + "What is your name? ")
     Dim name = Console.ReadLine()
     Dim currentDate = DateTime.Now
     Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}")
     Console.Write(vbCrLf + "Press any key to exit... ")
     Console.ReadKey(True)
    ```

    Ce code remplace les instructions <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A> et <xref:System.Console.ReadKey%2A> existantes.

   ![Fenêtre de code affichant le code « Quel est votre nom »](./media/vs-2019/vb-codewindow-what-name-dark.png)

1. Quand la fenêtre de console s’ouvre, entrez votre nom. La fenêtre de console doit ressembler à la capture d’écran suivante :

   ![Fenêtre de console qui affiche What Is Your Name, la date et l’heure, et le message Press any key to continue](media/vb-console-what-name.png)

1. Appuyez sur une touche pour fermer la fenêtre de console.

::: moniker-end

::: moniker range="vs-2019"

1. Dans le projet *WhatIsYourName*, entrez le code Visual Basic suivant juste après le crochet ouvrant qui suit la ligne `Sub Main(args As String())` et avant la ligne `End Sub` :

     ```vb
     Console.WriteLine(vbCrLf + "What is your name? ")
     Dim name = Console.ReadLine()
     Dim currentDate = DateTime.Now
     Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}")
     Console.Write(vbCrLf + "Press any key to exit... ")
     Console.ReadKey(True)
    ```

    Ce code remplace les instructions <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A> et <xref:System.Console.ReadKey%2A> existantes.

   ![Fenêtre de code affichant le code « Quel est votre nom »](./media/vs-2019/vb-codewindow-what-name-dark.png)

1. Quand la fenêtre de console s’ouvre, entrez votre nom. La fenêtre de console doit ressembler à la capture d’écran suivante :

   ![Fenêtre de console qui affiche What Is Your Name, la date et l’heure, et le message Press any key to continue](media/vb-console-what-name.png)

1. Appuyez sur une touche pour fermer la fenêtre de console.

 ::: moniker-end

## <a name="create-a-calculate-this-application"></a>Créer une application « Calculer ceci »

::: moniker range="vs-2017"

1. Ouvrez Visual Studio 2017 puis, dans la barre de menus supérieure, choisissez **Fichier** > **Nouveau** > **Projet**.

1. Dans la boîte de dialogue **Nouveau projet**, dans le volet gauche, développez **Visual Basic**, puis choisissez **.NET Core**. Dans le volet central, choisissez **Application console (.NET Core)**. Ensuite, nommez le fichier *CalculateThis*.

1. Entrez le code suivant entre les lignes `Module Program` et `End Module` :

   ```vb
   Public num1 As Integer
   Public num2 As Integer
   Public answer As Integer
   Sub Main()
       Console.WriteLine("Type a number and press Enter")
       num1 = Console.ReadLine()
       Console.WriteLine("Type another number to add to it and press Enter")
       num2 = Console.ReadLine()
       answer = num1 + num2
       Console.WriteLine("The answer is " & answer)
       Console.ReadLine()
   End Sub
   ```

   La fenêtre de code doit ressembler à la capture d’écran suivante :

   ![Fenêtre de code montrant le code de CalculateThis](media/vb-codewindow-calculate-this.png)

1. Cliquez sur **CalculateThis** pour exécuter votre programme. La fenêtre de console doit ressembler à la capture d’écran suivante :

    ![Fenêtre de console montrant l’application CalculateThis, qui comprend des invites sur les actions à effectuer.](media/vb-console-calculate-this.png)

::: moniker-end 

::: moniker range="vs-2019"

1. Dans la fenêtre de démarrage, choisissez **Créer un projet**. 

1. Dans la fenêtre **Créer un projet**, entrez ou tapez *console* dans la zone de recherche. Ensuite, choisissez **Visual Basic** dans la liste des langages, puis choisissez **Windows** dans la liste des plateformes. 

1. Après avoir appliqué les filtres de langage et de plateforme, choisissez le modèle **Application console (.NET Core)**, puis choisissez **Suivant**.

   Ensuite, dans la fenêtre **Configurer votre nouveau projet**, tapez ou entrez *WhatIsYourName* dans la zone **Nom du projet**. Ensuite, choisissez **Créer**.

1. Entrez le code suivant entre les lignes `Module Program` et `End Module` :

   ```vb
   Public num1 As Integer
   Public num2 As Integer
   Public answer As Integer
   Sub Main()
       Console.WriteLine("Type a number and press Enter")
       num1 = Console.ReadLine()
       Console.WriteLine("Type another number to add to it and press Enter")
       num2 = Console.ReadLine()
       answer = num1 + num2
       Console.WriteLine("The answer is " & answer)
       Console.ReadLine()
   End Sub
   ```

   La fenêtre de code doit ressembler à la capture d’écran suivante :

   ![Fenêtre de code montrant le code de CalculateThis](media/vb-codewindow-calculate-this.png)

1. Cliquez sur **CalculateThis** pour exécuter votre programme. La fenêtre de console doit ressembler à la capture d’écran suivante :

    ![Fenêtre de console montrant l’application CalculateThis, qui comprend des invites sur les actions à effectuer.](media/vb-console-calculate-this.png)

::: moniker-end

## <a name="quick-answers-faq"></a>Questions fréquentes (FAQ) et réponses rapides

Voici des Questions fréquentes (FAQ) rapides pour mettre en lumière certains concepts clés.

### <a name="what-is-visual-basic"></a>Qu’est-ce que Visual Basic ?

Visual Basic est un langage de programmation de type sécurisé conçu pour être facile à apprendre. Il est dérivé du langage BASIC, qui signifie « Beginner’s All-purpose Symbolic Instruction Code ».

### <a name="what-is-visual-studio"></a>Qu’est-ce que Visual Studio ?

Visual Studio est une suite de développement intégrée d’outils de productivité pour les développeurs. Il s’agit d’un programme qui sert à créer des applications et des programmes.

### <a name="what-is-a-console-app"></a>Qu’est-ce qu’une application console ?

Une application console prend une entrée et affiche la sortie dans une fenêtre de ligne de commande, également appelée console.

### <a name="what-is-net-core"></a>Qu'est-ce que le .NET Core ?

.NET Core est la suite logique du .NET Framework. Là où le .NET Framework vous permettait de partager du code entre les langages de programmation, .NET Core ajoute la capacité à partager du code entre des plateformes. De plus, il est open source. (Le .NET Framework et .NET Core incluent des bibliothèques de fonctionnalités prégénérées ainsi qu’un CLR (Common Language Runtime) qui agit comme une machine virtuelle dans laquelle exécuter votre code.)

## <a name="next-steps"></a>Étapes suivantes

Félicitations ! Vous avez terminé ce didacticiel. Pour en apprendre davantage, consultez le tutoriel suivant.

> [!div class="nextstepaction"]
> [Générer une bibliothèque avec Visual Basic et le SDK .NET Core dans Visual Studio](/dotnet/core/tutorials/vb-library-with-visual-studio)

## <a name="see-also"></a>Voir aussi

* [Procédures pas à pas relatives au langage Visual Basic](/dotnet/visual-basic/walkthroughs)
* [Références du langage Visual Basic](/dotnet/visual-basic/language-reference/index)
* [IntelliSense pour les fichiers de code Visual Basic](../../ide/visual-basic-specific-intellisense.md)
