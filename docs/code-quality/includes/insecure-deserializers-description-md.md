---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 054198eff46c0983a5610b29dee5e29e5ac67a70
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65840911"
---
Désérialiseurs non sécurisés sont vulnérables lors de la désérialisation des données non fiables. Un attaquant pourrait modifier les données sérialisées pour inclure les types inattendus pour injecter des objets ayant des effets nuisibles. Une attaque contre un désérialiseur non sécurisé peut, par exemple, exécuter des commandes sur le système d’exploitation sous-jacent, communiquer sur le réseau ou supprimer des fichiers.