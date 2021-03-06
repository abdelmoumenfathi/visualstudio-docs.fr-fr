---
title: Mapper les méthodes sur la pile des appels tout en déboguant
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8641a677ae36ad5a3c1f0f4344fc5c12b8798d7d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63445141"
---
# <a name="map-methods-on-the-call-stack-while-debugging-in-visual-studio"></a>Mapper les méthodes sur la pile des appels tout en déboguant dans Visual Studio

Créez une carte de code pour effectuer un suivi visuel de la pile des appels pendant le débogage. Vous pouvez rédiger des notes sur la carte pour effectuer le suivi de ce que fait le code afin de vous concentrer sur la recherche de bogues.

 ![Débogage avec des piles d’appels sur des cartes de code](../debugger/media/debuggermap_overview.png)

 Vous aurez besoin de :

 ::: moniker range="vs-2017"

- [Visual Studio Enterprise](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download)

::: moniker-end

::: moniker range="vs-2019"

- [Visual Studio Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

::: moniker-end

- Code que vous pouvez déboguer, tels que Visual C#, Visual Basic, C++, JavaScript ou X ++

  Consultez :

- [Vidéo : Déboguez visuellement avec intégration du débogueur (Channel 9)](http://go.microsoft.com/fwlink/?LinkId=293418)

- [Mapper la pile des appels](#MapStack)

- [Rédiger des notes sur le code](#MakeNotes)

- [Mettre à jour de la carte avec la pile d’appels suivante](#UpdateMap)

- [Ajouter du code associé à la carte](#AddRelatedCode)

- [Rechercher des bogues à l’aide de la carte](#FindBugs)

- [Q &AMP; R](#QA)

  Pour des informations sur les commandes et les actions que vous pouvez utiliser lorsque vous travaillez avec des cartes de code, consultez [Parcourir et réorganiser des cartes de code](../modeling/browse-and-rearrange-code-maps.md).

## <a name="MapStack"></a> Mapper la pile des appels

1. Démarrez le débogage. (Clavier : **F5**)

2. Une fois que votre application passe en mode arrêt ou que vous parcourez une fonction, choisissez **carte de Code**. (Clavier : **Ctrl** + **Shift** + **`**)

     ![Choisir Carte de code pour démarrer le mappage de la pile d’appels](../debugger/media/debuggermap_choosecodemap.png)

     La pile d’appels actuelle apparaît en orange sur une nouvelle carte de code :

     ![Voir pile d’appels sur carte de code](../debugger/media/debuggermap_seeundocallstack.png)

     La carte se mettra à jour automatiquement pendant que vous continuez le débogage. Consultez [mettre à jour de la carte avec la pile d’appels suivante](#UpdateMap).

## <a name="MakeNotes"></a> Rédiger des notes sur le code

 Ajouter des commentaires pour effectuer le suivi de ce qui se passe dans le code. Pour ajouter une nouvelle ligne dans un commentaire, appuyez sur **MAJ + ENTRÉE**.

 ![Ajouter un commentaire à la pile d’appels sur la carte de code](../debugger/media/debuggermap_addcomment.png)

## <a name="UpdateMap"></a> Mettre à jour la carte avec la pile d’appels suivante

 Exécutez votre application jusqu'au point d'arrêt suivant ou exécutez pas à pas une fonction. La carte ajoute une nouvelle pile d'appels.

 ![Mettre à jour la carte de code avec la pile d’appels suivante](../debugger/media/debuggermap_addclearcallstack.png)

## <a name="AddRelatedCode"></a> Ajouter du code associé à la carte

 Vous disposez maintenant une carte - ce qu’ensuite ? Si vous travaillez avec C# ou Visual Basic, ajoutez des éléments, tels que des champs, propriétés et d’autres méthodes, pour effectuer le suivi de ce qui se passe dans le code.

 Double-cliquez sur une méthode pour afficher sa définition de code ou utilisez le menu contextuel pour la méthode. (Clavier : Sélectionnez la méthode sur la carte et appuyez sur **F12**)

 ![Aller à la définition du code pour une méthode sur une carte du code](../debugger/media/debuggermap_gotocodedefinition.png)

 Ajoutez les éléments que vous souhaitez suivre sur la carte.

 ![Afficher les champs dans une méthode sur la carte de code de la pile d’appels](../debugger/media/debuggermap_showfields.png)

> [!NOTE]
> Par défaut, l'ajout d'éléments à la carte ajoute également les nœuds des groupes parents, comme la classe, l'espace de noms et l'assembly. Bien que cela soit utile, vous pouvez conserver le mappage simple en désactivant cette fonctionnalité à l’aide de la **inclure les Parents** bouton sur la barre d’outils de mappage, ou en appuyant sur **CTRL** lorsque vous ajoutez des éléments.

 ![Champs associés à une méthode sur la carte du code de la pile d’appels](../debugger/media/debuggermap_showedfields.png)

 Vous pouvez ici voir aisément quelles méthodes utilisent les mêmes champs. Les derniers éléments ajoutés apparaissent en vert.

 Poursuivez l'élaboration de la carte pour afficher davantage de code.

 ![Voir les méthodes qui utilisent un champ : carte du code de la pile d’appels](../debugger/media/debuggermap_findallreferences.png)

 ![Méthodes qui utilisent un champ sur la carte du code de la pile d’appels](../debugger/media/debuggermap_foundallreferences.png)

## <a name="FindBugs"></a> Rechercher des bogues à l’aide de la carte

 La visualisation de votre code peut vous aider à rechercher des bogues plus rapidement. Par exemple, supposons que vous recherchiez un bogue dans un programme de dessin. Lorsque vous tracez une ligne et essayez de l'annuler, rien ne se produit jusqu'à ce que vous traciez une autre ligne.

 Vous définissez donc des points d'arrêt dans les méthodes `clear`, `undo` et `Repaint`, vous démarrez le débogage et vous générez une carte comme celle-ci :

 ![Ajouter une autre pile d’appels à la carte de code](../debugger/media/debuggermap_addpaintobjectcallstack.png)

 Vous constatez que tous les mouvements de l'utilisateur sur la carte appellent `Repaint`, à l'exception de `undo`. Cela peut expliquer pourquoi `undo` ne fonctionne pas immédiatement.

 Après avoir corrigé le bogue et poursuivi l'exécution du programme, la carte ajoute le nouvel appel de `undo` à `Repaint` :

 ![Ajouter un nouvel appel de méthode à la pile d’appels sur le code de mappage](../debugger/media/debuggermap_addnewcallforrepaint.png)

## <a name="QA"></a> Q et R

- **Pas tous les appels apparaissent sur la carte. Pourquoi ?**

   Par défaut, seul votre propre code apparaît sur la carte. Pour afficher le code externe, activez-le dans la **pile des appels** fenêtre :

   ![Afficher du code externe à l'aide de la fenêtre Pile des appels](../debugger/media/debuggermap_callstackmenu.png)

   ou désactivez **activer uniquement mon Code** dans les options de débogage Visual Studio :

   ![Afficher du code externe à l'aide de la boîte de dialogue Options](../debugger/media/debuggermap_debugoptions.png)

- **Modification de la carte affecte-t-elle le code ?**

   Modification de la carte n’affecte pas le code en aucune façon. N'hésitez pas à renommer, déplacer ou supprimer tout élément de la carte.

- **Que signifie ce message : « Le diagramme peut être basé sur une version antérieure du code » ?**

   Il se peut que le code ait changé après la dernière mise à jour de la carte. Par exemple, un appel sur la carte peut ne plus exister dans le code. Fermez le message et essayez de régénérer la solution avant de remettre à jour la carte.

- **Comment contrôler la disposition de la carte ?**

   Ouvrez le **disposition** menu sur la barre d’outils de mappage :

  - Modifiez la disposition par défaut.

  - Pour arrêter la réorganisation automatique de la carte, désactivez **disposer automatiquement lors du débogage**.

  - Pour réorganiser la carte aussi peu que possible lorsque vous ajoutez des éléments, désactivez **disposition incrémentielle**.

- **Puis-je partager la carte avec d’autres personnes ?**

   Vous pouvez exporter la carte, l’envoyer à d’autres personnes si vous disposez de Microsoft Outlook ou enregistrez dans votre solution afin de vérifier dans le contrôle de code source.

   ![Partager la carte du code de la pile d'appels avec les autres](../debugger/media/debuggermap_sharewithothers.png)

- **Comment empêcher le mappage de l’ajout de nouvelles piles d’appels automatiquement ?**

   Choisissez ![bouton &#45; pile des appels de l’afficher sur la carte de code automatiquement](../debugger/media/debuggermap_automaticupdateicon.gif) sur la barre d’outils de la carte. Pour ajouter manuellement la pile des appels actuelle à la carte, appuyez sur **Ctrl** + **MAJ** + **`**.

   La carte continuera à être mise en surbrillance les piles d’appels existantes sur la carte pendant que vous déboguez.

- **Que les icônes de l’élément et les flèches signifient ?**

   Pour obtenir plus d’informations sur un élément, placez le pointeur de la souris dessus et consultez l’info-bulle. Vous pouvez également consulter le **légende** pour savoir ce que signifie chaque icône.

   ![Que signifient les icônes sur la carte du code de la pile d’appels ?](../debugger/media/debuggermap_showlegend.png)

  Consultez :

- [Mapper la pile des appels](#MapStack)

- [Rédiger des notes sur le code](#MakeNotes)

- [Mettre à jour de la carte avec la pile d’appels suivante](#UpdateMap)

- [Ajouter du code associé à la carte](#AddRelatedCode)

- [Rechercher des bogues à l’aide de la carte](#FindBugs)

## <a name="see-also"></a>Voir aussi

- [Mapper les dépendances à travers vos solutions](../modeling/map-dependencies-across-your-solutions.md)
- [Utiliser des cartes de code pour déboguer vos applications](../modeling/use-code-maps-to-debug-your-applications.md)
- [Rechercher des problèmes potentiels à l’aide des analyseurs de carte du code](../modeling/find-potential-problems-using-code-map-analyzers.md)
- [Parcourir et réorganiser des cartes de code](../modeling/browse-and-rearrange-code-maps.md)
