---
title: Application des paramètres entre plusieurs connexions de projet | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, application of settings
ms.assetid: 2116d3d0-c46c-4d0a-b482-08a178584f46
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6dbc2638fa23a1e0c7bf1301c3c978a1ef864c75
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62861678"
---
# <a name="application-of-settings-across-multiple-project-connections"></a>Application des paramètres entre plusieurs connexions de projet
Un plug-in de contrôle de code source créé à l’aide de la Source de contrôle plug-in API Version 1.2, peut utiliser une opération par lot pour exécuter l’opération de contrôle de code source même entre plusieurs projets ou de plusieurs contextes de connexion. Lots peuvent être utilisés pour éliminer redondants, des boîtes de dialogue à partir de l’expérience utilisateur par projet.

 Si un utilisateur sélectionne plusieurs éléments qui appartiennent à plusieurs connexions dans un plug-in de contrôle de code source créée à l’aide de l’API Version 1.1 (par exemple, deux les projets web sur le partage de fichiers différentes machines) Source contrôle plug-in et les vérifie, l’utilisateur voit le même la boîte de dialogue à plusieurs reprises. Ce scénario se produit même si l’utilisateur clique sur le **appliquer à tous** case à cocher dans la boîte de dialogue, car l’IDE réinitialise son état pour chaque contexte de connexion.

## <a name="new-capability-flag"></a>Nouvel indicateur de fonctionnalité
 Le `SccBeginBatch` fonction définit la `SCC_CAP_BATCH` indicateur pour indiquer qu’une opération par lot est en cours.

## <a name="new-functions"></a>Nouvelles fonctions
Les fonctions suivantes prennent en charge l’opération de traitement par lots :

- [SccBeginBatch](../../extensibility/sccbeginbatch-function.md)

- [SccEndBatch](../../extensibility/sccendbatch-function.md)

Le `SCCBeginBatch` fonction commence à un groupe d’opérations de contrôle de code source. Le `SccEndBatch` fonction ferme le groupe. Les groupes ne peuvent pas être imbriqués.

## <a name="see-also"></a>Voir aussi
- [Nouveautés de la Version 1.2 des API de plug-in de contrôle Source](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)