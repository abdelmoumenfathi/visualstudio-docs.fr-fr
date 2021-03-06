---
title: -LCID (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- language default
- locale IDs, setting for IDE
- Devenv, /L switch
- Devenv, /LCID switch
- locale IDs
- L Devenv switch
- /L Devenv switch
- LCID devenv switch
- /LCID Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: deb2ce5eba108127dce82bab77fe7ed4fb78fb14
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62970125"
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)

Définit la langue utilisée par défaut pour le texte, la devise et d’autres valeurs de l’environnement IDE.

## <a name="syntax"></a>Syntaxe

```shell
devenv {/LCID|/L} LocaleID
```

## <a name="arguments"></a>Arguments

- *LocaleID*

  Obligatoire. Identificateur de paramètres régionaux (LCID) de la langue spécifiée.

## <a name="remarks"></a>Remarques

Charge l’IDE et définit le langage naturel par défaut pour l’environnement. Cette modification est persistante d’une session à l’autre, et l’environnement IDE affiche cette modification dans la zone **Outils** > **Options** > **Environnement** > **Paramètres internationaux** > **Langue**.

Si la langue spécifiée n’est pas disponible sur le système, le commutateur `/LCID` est ignoré.

Le tableau suivant indique les identificateurs LCID des langues prises en charge par Visual Studio.

|Langue|dans le dossier HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\|
|--------------|----------|
|Chinois (simplifié)|2052|
|Chinois (traditionnel)|1028|
|Anglais|1033|
|Français|1036|
|Allemand|1031|
|Italien|1040|
|Japonais|1041|
|Coréen|1042|
|Espagnol|3082|

## <a name="example"></a>Exemple

Cet exemple charge l’IDE avec des chaînes de ressources en anglais.

```shell
devenv /LCID 1033
```

## <a name="see-also"></a>Voir aussi

- [Commutateurs de ligne de commande Devenv](../../ide/reference/devenv-command-line-switches.md)
- [Paramètres internationaux, Environnement, boîte de dialogue Options](../../ide/reference/international-settings-environment-options-dialog-box.md)
- [Personnalisation des dispositions de fenêtres](../../ide/customizing-window-layouts-in-visual-studio.md)