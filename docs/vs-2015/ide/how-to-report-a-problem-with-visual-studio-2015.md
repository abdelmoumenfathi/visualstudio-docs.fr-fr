---
title: Guide pratique pour signaler un problème avec Visual Studio 2015 | Microsoft Docs
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.topic: conceptual
ms.assetid: 24ecb76e-b7ad-432d-88ab-d9849963465d
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d8cedd5ab26539d5ebe32aee8df272691dd0a779
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60083647"
---
# <a name="how-to-report-a-problem-with-visual-studio-2015"></a>Guide pratique pour signaler un problème avec Visual Studio 2015
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour consulter la documentation à jour sur Visual Studio, voir [Guide pratique pour signaler un problème dans Visual Studio](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).

Si vous rencontrez un problème avec Visual Studio 2015, faites-nous-en part pour que nous puissions le diagnostiquer et le résoudre.  L’outil **Signaler un problème** vous permet de recueillir des informations détaillées sur le problème et de les envoyer à Microsoft en seulement quelques clics.

Microsoft respecte votre vie privée. Pour plus d’informations sur la façon dont nous utilisons les données que vous nous envoyez, consultez [Déclaration de confidentialité des produits Microsoft Visual Studio](https://www.visualstudio.com/dn948229).

## <a name="open-the-report-a-problem-tool"></a>Ouvrir l’outil Signaler un problème

Cliquez sur l’icône des commentaires utilisateur à côté de **Lancement rapide** dans la barre de titre, ou sur **Aide > Envoyer des commentaires > Signaler un problème**.

![Élément de menu Signaler un problème](../ide/media/report-a-problem-menu-item.png "Élément de menu Signaler un problème")

## <a name="describe-the-problem"></a>Décrire le problème

### <a name="describe_the_problem"></a>

1. Donnez un titre descriptif au problème qui nous aidera à l’adresser à l’équipe Visual Studio appropriée.

2. Indiquez des détails supplémentaires et, si possible, la procédure permettant de reproduire le problème.

3. Choisissez un secteur qui pose problème dans la liste déroulante. Indiquez l’hypothèse qui vous semble la meilleure si vous n’avez aucune certitude.

   ![Signaler un problème, boîte de dialogue](../ide/media/report-a-problem-dialog.png "Signaler un problème, boîte de dialogue")

## <a name="provide-a-screenshot-optional"></a>Fournir une capture d’écran (facultatif)

Choisissez **Inclure une capture d’écran** pour envoyer l’écran actuellement affiché à Microsoft. L’outil permet de rogner l’image de façon à ne montrer que la partie de l’écran qui illustre le problème. Vous pouvez joindre d’autres captures d’écran ou fichiers en cliquant sur le bouton **Joindre des fichiers supplémentaires** .

## <a name="provide-a-trace-and-heap-dump-optional"></a>Fournir un fichier dump de tas et de suivi (facultatif)

### <a name="provide_a_trace_and_heap_dump"></a>

1. Les fichiers dump de tas et de suivi s’avèrent très utiles pour nous aider à diagnostiquer les problèmes.   Nous vous remercions beaucoup d’employer l’outil Signaler un problème pour enregistrer les étapes de reproduction du problème ainsi que d’envoyer les données à Microsoft.

2. Cliquez sur le chevron en regard de **Enregistrez vos actions pour reproduire le problème**. Si le problème est tel que Visual Studio se bloque ou tombe en panne, ouvrez une autre instance de Visual Studio et sélectionnez-la dans l’affichage de liste.

3. Cliquez sur **Démarrer l’enregistrement** et effectuez les étapes pour reproduire le problème. Quand vous avez terminé, cliquez sur le bouton **Arrêter l’enregistrement** dans la fenêtre flottante.

4. Attendez quelques minutes que Visual Studio collecte et compresse les informations qui ont été enregistrées. La boîte de dialogue ressemble à ceci quand le processus de collection est terminé :

     ![Enregistrer un fichier de trace](../ide/media/record-a-trace-file.png "Enregistrer un fichier de trace")

## <a name="describe-the-workaround-if-there-is-one"></a>Décrire la solution de contournement, le cas échéant

Si vous avez réussi à contourner le problème, décrivez la solution de contournement dans la zone prévue à cet effet. Ceci nous permet non seulement de diagnostiquer le problème, mais également d’aider les autres utilisateurs qui peuvent rencontrer le même problème.

## <a name="submit-the-report"></a>Envoyer le rapport

Cliquez sur le bouton Envoyer pour envoyer votre rapport, ainsi que les images et les fichiers dump ou de suivi. Si le bouton **Envoyer** est grisé, vérifiez que vous avez fourni un titre et une description.

## <a name="see-also"></a>Voir aussi

- [Nous contacter](../ide/talk-to-us.md)
