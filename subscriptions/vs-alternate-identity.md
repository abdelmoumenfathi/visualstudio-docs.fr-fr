---
title: Identités pour les abonnés Visual Studio
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 04/10/2018
ms.topic: conceptual
description: Comment ajouter une identité secondaire à votre abonnement Visual Studio pour l’utiliser avec Azure DevOps et Azure
searchscope: vs subscription
ms.openlocfilehash: 63a372d4a0e0e70a008f86a36aae73516bf42458
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62428074"
---
# <a name="identities-for-visual-studio-subscribers"></a>Identités pour les abonnés Visual Studio

Quand vous activez votre abonnement Visual Studio, nous lions l’identité (ou connexion) que vous avez utilisée lors de l’activation avec l’abonnement Visual Studio. Ainsi, nous pouvons vous reconnaître dans le [portail des abonnés Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), dans Azure DevOps et dans Azure.

Dans Azure DevOps, nous vérifions l’état de votre abonnement Visual Studio chaque fois que vous vous connectez, et nous vous octroyons des fonctionnalités automatiquement dans chaque organisation dont vous êtes membre.
Ces fonctionnalités étant incluses comme avantages réservés aux abonnés, il est possible de vous ajouter gratuitement comme membre de n’importe quelle organisation Azure DevOps lors de l’utilisation d’une identité qui est liée à votre abonnement Visual Studio.

Dans Azure, nous vérifions l’état de votre abonnement Visual Studio quand vous activez votre [crédit Azure mensuel](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) qui est un avantage réservé aux abonnés.

Dans le [portail des abonnés Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), vous pouvez éventuellement ajouter une **identité secondaire**, en plus de celle que vous avez utilisée durant l’activation. Aujourd’hui, nous vous permettons d’ajouter une identité secondaire, si vous avez utilisé un compte Microsoft pour activer votre abonnement. Ainsi, vous pouvez également ajouter un compte professionnel ou scolaire (que vous utilisez pour vous connecter à Visual Studio, à Office 365 ou à votre réseau d’entreprise ou d’établissement scolaire), ce qui vous permet d’accéder à Azure DevOps à la fois avec votre compte personnel, et avec votre compte professionnel ou scolaire.

## <a name="add-an-alternate-account-to-your-visual-studio-subscription"></a>Ajouter un compte secondaire à votre abonnement Visual Studio

L’ajout d’un compte secondaire à votre abonnement Visual Studio vous permet d’accéder aux avantages de cet abonnement, par exemple Azure DevOps et Azure, avec une autre identité que celle à laquelle l’abonnement est affecté. Dans le passé, cette fonctionnalité était disponible uniquement si votre abonnement VS (Visual Studio) était affecté à un compte MSA (compte Microsoft). Nous avons étendu cette fonctionnalité aux comptes professionnels ou scolaires dans Azure AD (Azure Active Directory).

Cela ne signifie pas que vous avez une copie de l’abonnement pour l’autre compte. En fait, cela signifie que vous pouvez accéder aux deux avantages avec le compte secondaire.

Pour tous les abonnements, vous pouvez ajouter un « compte professionnel ou scolaire », ce qui vous permet d’utiliser ce compte avec les avantages nécessitant une connexion (IDE VS, Azure DevOps et Azure).

### <a name="add-the-alternate-account"></a>Ajouter le compte secondaire

1. Connectez-vous au portail des abonnés Visual Studio à l’aide de votre compte Microsoft (https://my.visualstudio.com).

2. Accédez à **Abonnements**.

    > [!div class="mx-imgBorder"]
    > ![Ajouter un compte secondaire - Accéder aux abonnements dans le portail VS](_img/vs-alternate-identity/my-vs-subscriptions.png)

3. Choisissez **Ajouter un compte secondaire**.
    > [!div class="mx-imgBorder"]
    > ![Choisir Ajouter un compte secondaire ](_img/vs-alternate-identity/choose-add-alternate-account.png)

4. Ajoutez votre compte professionnel ou scolaire.
    > [!div class="mx-imgBorder"]
    > ![Ajouter un compte professionnel ou scolaire](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. Utilisez votre compte professionnel ou scolaire pour vous connecter à Azure DevOps (https://{votre_compte}.visualstudio.com).
    > [!div class="mx-imgBorder"]
    > ![Utiliser votre compte professionnel ou scolaire](_img/vs-alternate-identity/sign-in-with-alternate-account.png)

Votre compte secondaire est ajouté à l’abonnement Visual Studio. Ainsi, les deux identités peuvent utiliser les avantages de l’abonnement qui vous imposent de vous connecter avec le compte secondaire (IDE, Azure DevOps et Azure).

## <a name="faq"></a>Questions fréquentes (FAQ)

### <a name="q--why-doesnt-azure-devops-recognize-me-as-a-visual-studio-subscriber"></a>Q :  Pourquoi Azure DevOps ne me reconnaît-il pas en tant qu’abonné Visual Studio ?

R : Azure DevOps doit reconnaître automatiquement votre abonnement quand vous vous connectez à l’aide de votre identité principale ou secondaire. Si ce n’est pas le cas, vous pouvez essayer les solutions suivantes :

* Vérifiez que vous disposez d’un abonnement Visual Studio actif qui [inclut Azure DevOps en tant qu’avantage](vs-azure-devops.md).

* Vérifiez que vous utilisez une connexion/identité qui est l’identité principale ou secondaire de votre abonnement Visual Studio.

* Accédez au [portail des abonnés Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs) au moins une fois avant de vous connecter à Azure DevOps.

Si Azure DevOps ne reconnaît toujours pas votre abonnement, [contactez le support technique](https://visualstudio.microsoft.com/team-services/support/)
