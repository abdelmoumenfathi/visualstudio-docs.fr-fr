---
title: Enregistrer la sortie de la fenêtre de commande, commande
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- tools.logcommandwindowoutput
helpviewer_keywords:
- log Command window output command
- View.LogCommandWindowOutput command
ms.assetid: d4ecec35-5af4-4954-8d60-2cd24583fbb4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 24c72b0c5aeb510186728d66e51935c337547adf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946841"
---
# <a name="log-command-window-output-command"></a>Enregistrer la sortie de la fenêtre de commande, commande
Copie toutes les entrées et sorties de la fenêtre **Commande** dans un fichier.

## <a name="syntax"></a>Syntaxe

```cmd
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]
```

## <a name="arguments"></a>Arguments
 `filename`

 Optionnel. Nom du fichier journal. Par défaut, le fichier est créé dans le dossier du profil de l’utilisateur. Si le nom de fichier existe déjà, le journal est ajouté à la fin du fichier existant. Si aucun fichier n’est spécifié, le dernier fichier spécifié est utilisé. Si aucun fichier n’a été spécifié précédemment, le fichier journal cmdline.log est créé par défaut.

> [!TIP]
> Pour modifier l’emplacement d’enregistrement du fichier journal, entrez le chemin complet du fichier, en l’entourant de guillemets s’il comporte des espaces.

## <a name="switches"></a>Commutateurs
 /on

 Optionnel. Démarre le journal pour la fenêtre **Commande** dans le fichier spécifié et ajoute les nouvelles informations à la fin de ce fichier.

 /off

 Optionnel. Arrête le journal pour la fenêtre **Commande**.

 /overwrite

 Optionnel. Si le fichier spécifié dans l’argument `filename` est identique à un fichier existant, celui-ci est remplacé.

## <a name="remarks"></a>Remarques
 Si aucun fichier n’est spécifié, le fichier cmdline.log est créé par défaut. L’alias par défaut de cette commande est Log.

## <a name="examples"></a>Exemples
 Cet exemple crée le fichier journal cmdlog, puis démarre l’enregistrement des commandes.

```cmd
>Tools.LogCommandWindowOutput cmdlog
```

 Cet exemple arrête l’enregistrement des commandes.

```cmd
>Tools.LogCommandWindowOutput /off
```

 Cet exemple reprend l’enregistrement des commandes dans le dernier fichier journal utilisé.

```cmd
>Tools.LogCommandWindowOutput /on
```

## <a name="see-also"></a>Voir aussi

- [Commandes Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Commande, fenêtre](../../ide/reference/command-window.md)
- [Rechercher/Commande, zone](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)