---
title: Lancement rapide, Environnement, boîte de dialogue Options
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.QuickLaunch
- vs.quicklaunch
helpviewer_keywords:
- searching IDE
- IDE, searching
ms.assetid: 4200f297-d065-4723-9a30-d91ff2e26c9d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
monikerRange: vs-2017
ms.openlocfilehash: a67e909dc43f17e12dd63b7a8a3b2e8a4afacc5e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62969044"
---
# <a name="quick-launch-environment-options-dialog-box"></a>Lancement rapide, Environnement, boîte de dialogue Options

Vous pouvez utiliser **Lancement rapide** pour rechercher et exécuter rapidement des actions pour les ressources de l’IDE, comme les options, les modèles ou les menus. Vous ne pouvez pas utiliser **Lancement rapide** pour rechercher du code et des symboles. La zone de recherche **Lancement rapide** se trouve en haut à droite de la barre de menus et est accessible en appuyant sur **Ctrl**+**Q**. Tapez votre chaîne de recherche dans la zone. Pour rechercher des chaînes qui contiennent des @, utilisez @@.

L’option **Lancement rapide** est activée par défaut quand vous installez Visual Studio. Dans la barre de menus, vous pouvez afficher ou masquer **Lancement rapide** en choisissant **Outils** > **Options**. Développez le nœud **Environnements**, puis choisissez **Lancement rapide**. Cochez ou décochez la case **Activer le menu de lancement rapide**. Vous pouvez également activer ou désactiver des catégories de recherche sur cette page.

## <a name="category-list"></a>Liste des catégories

Les résultats de recherche de Lancement rapide apparaissent dans quatre catégories : **Utilisés le plus récemment**, **Menus**, **Options** et **Documents ouverts**, avec le nombre d’éléments de la catégorie. Pour parcourir les résultats de la recherche par catégorie, choisissez les touches **Ctrl**+**Q** pour afficher tous les résultats de la catégorie suivante. Une fois la dernière catégorie affichée, **Ctrl**+**Q** vous montre quelques résultats de chaque catégorie. Appuyez sur **Ctrl**+**Maj**+**Q** pour naviguer dans les catégories dans l’ordre inverse. Pour afficher tous les résultats de recherche d'une catégorie, choisissez le nom de la catégorie.

Vous pouvez utiliser les raccourcis suivants pour limiter votre recherche à des catégories spécifiques.

|Category|Raccourci|Description du raccourci|
|--------------|--------------| - |
|Les dernières utilisées|@mru<br /><br /> Par exemple, `@mru font`.|Affiche jusqu’à cinq des éléments que vous avez **utilisés le plus récemment**.|
|Menus|@menu<br /><br /> Par exemple, `@menu project`.|Limite la recherche aux éléments de menu.|
|Options|@opt<br /><br /> Par exemple, `@opt font`.|Limite la recherche aux paramètres de la boîte de dialogue **Options**.|
|Documents|@doc<br /><br /> Par exemple, `@doc program.cs`.|Limite la recherche aux noms et aux chemins d'accès de fichiers des documents ouverts pour les critères de recherche, mais ne recherche pas le texte dans les fichiers eux-mêmes.|

> [!NOTE]
> Vous pouvez changer les touches de raccourci dans la page **Général** > **Clavier** de la boîte de dialogue **Options**.

## <a name="show-previous-results"></a>Afficher les résultats précédents

Par défaut, le terme de recherche que vous entrez n'est pas conservé entre les sessions de recherche. La chaîne de recherche est effacée si vous recherchez un terme, que vous déplacez le curseur en dehors de la zone **Lancement rapide**, puis que vous y revenez. Pour conserver les résultats de recherche, accédez à la boîte de dialogue **Options**, choisissez **Lancement rapide**, puis cochez la case **Afficher les résultats de la dernière recherche si le menu de lancement rapide est activé** . La prochaine fois que vous effectuez une recherche, quittez la zone Lancement rapide et revenez-y : la zone Lancement rapide conserve alors le dernier terme de recherche utilisé et vous montre également les résultats de recherche.

## <a name="see-also"></a>Voir aussi

- [Environnement, boîte de dialogue Options](../../ide/reference/environment-options-dialog-box.md)
