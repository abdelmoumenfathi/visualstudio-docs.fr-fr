---
title: UpdateManifest, tâche | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, UpdateManifest task
- UpdateManifest task [MSBuild]
ms.assetid: 1291fd33-b89e-4e15-8fb1-69f9625cf2d2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0dd2ddfdbe784a45badfd0138b41b1f5dbff8ec7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62954464"
---
# <a name="updatemanifest-task"></a>UpdateManifest (tâche)
Met à jour les propriétés sélectionnées dans un manifeste et signe à nouveau.

## <a name="parameters"></a>Paramètres
 Le tableau ci-dessous décrit les paramètres de la tâche `UpdateManifest` .

|Paramètre|Description|
|---------------|-----------------|
|`ApplicationManifest`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> requis.<br /><br /> Spécifie le manifeste d’application.|
|`ApplicationPath`|Paramètre `String` requis.<br /><br /> Spécifie le chemin du manifeste d’application.|
|`InputManifest`|Paramètre <xref:Microsoft.Build.Framework.ITaskItem> requis.<br /><br /> Spécifie le manifeste à mettre à jour.|
|`OutputManifest`|Paramètre de sortie <xref:Microsoft.Build.Framework.ITaskItem> facultatif.<br /><br /> Spécifie le manifeste qui contient les propriétés mises à jour.|

## <a name="remarks"></a>Remarques
 En plus des paramètres répertoriés dans le tableau, cette tâche hérite des paramètres de la classe <xref:Microsoft.Build.Utilities.Task>. Pour obtenir la liste de ces paramètres supplémentaires et leurs descriptions, consultez [Classe de base de tâche](../msbuild/task-base-class.md).

## <a name="see-also"></a>Voir aussi
- [Tâches](../msbuild/msbuild-tasks.md)
- [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)