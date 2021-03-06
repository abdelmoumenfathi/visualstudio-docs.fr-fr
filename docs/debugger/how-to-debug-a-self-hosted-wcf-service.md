---
title: 'Procédure : Déboguer un Service WCF auto-hébergé | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, self-hosted service
- WCF, debugging
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8440c1bae9d9e405fd0bf0e1462467e7a51dad5e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62848020"
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>Procédure : déboguer un service WCF auto-hébergé
Un *service auto-hébergé* est un service WCF qui ne s’exécute pas à l’intérieur d’IIS, de l’hôte de service WCF ni du serveur de développement [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]. Pour déboguer un service WCF auto-hébergé le plus simple consiste à configurer [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pour lancer le client et serveur lorsque vous choisissez **démarrer le débogage** sur le **déboguer** menu.

 Si le service WCF est auto-hébergé dans un processus qui ne peut pas être lancé de cette manière, tel que service NT, vous ne pouvez pas utiliser cette méthode. Au lieu de cela, vous pouvez effectuer l’une des opérations suivantes :

- Attacher manuellement le débogueur au processus d’hébergement. Pour plus d’informations, consultez [attacher aux processus en cours d’exécution](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).

     — ou —

- Démarrer le débogage du client et puis détaillé dans un appel au service. Cela nécessite que vous activez le débogage dans le fichier app.config. Pour plus d’informations, [Limitations du débogage WCF](../debugger/limitations-on-wcf-debugging.md).

### <a name="to-start-both-client-and-host-from-visual-studio"></a>Pour démarrer les clients et hôtes à partir de Visual Studio

1. Créer un [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] solution qui contient à la fois les projets client et serveur.

2. Configurer la solution pour démarrer le processus client et serveur lorsque vous choisissez **Démarrer** sur le **déboguer** menu.

   1. Dans **l’Explorateur de solutions**, cliquez sur le nom de la solution.

   2. Cliquez sur **définir les projets de démarrage**.

   3. Dans le **Solution \<nom > Propriétés** boîte de dialogue, sélectionnez **plusieurs projets de démarrage**.

   4. Dans le **plusieurs projets de démarrage** grille, sur la ligne qui correspond au projet serveur, cliquez sur **Action** et choisissez **Démarrer**.

   5. Sur la ligne qui correspond au projet client, cliquez sur **Action** et choisissez **Démarrer**.

   6. Cliquez sur **OK**.

## <a name="see-also"></a>Voir aussi
- [Débogage de services WCF](../debugger/debugging-wcf-services.md)
- [Limitations du débogage WCF](../debugger/limitations-on-wcf-debugging.md)
- [Guide pratique pour se lancer dans les services WCF](../debugger/how-to-step-into-wcf-services.md)