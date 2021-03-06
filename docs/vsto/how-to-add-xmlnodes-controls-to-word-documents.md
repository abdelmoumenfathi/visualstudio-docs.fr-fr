---
title: 'Procédure : Ajouter des contrôles XMLNodes à des documents Word'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLNodes control, adding to documents
- controls [Office development in Visual Studio], adding to documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b54a341cd9dd949f892537ee384afb4984aecc02
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63419692"
---
# <a name="how-to-add-xmlnodes-controls-to-word-documents"></a>Procédure : Ajouter des contrôles XMLNodes à des documents Word
  **Important** les informations mentionnées dans cette rubrique concernant Microsoft Word sont présentée exclusivement pour le bénéfice et l’utilisation des individus et les organisations qui se trouvent en dehors des États-Unis et ses territoires ou qui utilisent ou développement les programmes qui s’exécutent sur des produits de Microsoft Word qui ont été concédés sous licence par Microsoft avant janvier 2010, lorsque Microsoft supprimé une implémentation de fonctionnalités spécifiques liés à XML personnalisé à partir de Microsoft Word. Ces informations concernant Microsoft Word ne peuvent pas être lues ou utilisées par les individus ou organisations dans les États-Unis ou dans ses territoires qui sont à l’aide d’ou de développer des programmes qui s’exécutent sur des produits de Microsoft Word qui ont été concédés sous licence par Microsoft après le 10 janvier 2010 ; ces produits ne comportent pas le même que les produits sous licence avant cette date ou acheté et concédés sous licence pour une utilisation en dehors des États-Unis.

 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]

 Lorsque vous mappez un élément de schéma XML répétitif à un document Microsoft Office Word, Visual Studio ajoute automatiquement un <xref:Microsoft.Office.Tools.Word.XMLNodes> contrôle à votre document.

 Pour plus d’informations sur le mappage des éléments non répétés du schéma XML, consultez [Comment : Ajouter des contrôles XMLNode à des documents Word](../vsto/how-to-add-xmlnode-controls-to-word-documents.md).

> [!NOTE]
> Le <xref:Microsoft.Office.Tools.Word.XMLNodes> contrôle n’est pas disponible à partir de la **boîte à outils** ou le **des Sources de données** fenêtre, de la même manière il créé par programmation.

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

### <a name="to-add-an-xmlnodes-control-to-a-document"></a>Pour ajouter un contrôle XMLNodes à un document

1. Dans le document dans le concepteur Visual Studio, dans le ruban, cliquez sur le **développeur** onglet.

    > [!NOTE]
    > Si l'onglet **Développeur** n'est pas visible, vous devez tout d'abord l'afficher. Pour plus d'informations, voir [Procédure : Afficher l’onglet Développeur sur le ruban](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).

2. Dans le **XML** de groupe, cliquez sur **schéma**.

     Le **modèles et compléments** boîte de dialogue s’ouvre.

3. Cliquez sur le **schéma XML** onglet.

4. Cliquez sur **Ajouter schéma**.

     Le **ajouter un schéma** boîte de dialogue s’ouvre.

5. Sélectionnez un schéma XML qui contient les éléments de schéma extensible cliquez sur **Open**.

     Le **les paramètres de schéma** boîte de dialogue s’affiche.

6. Affecter un alias ou cliquez sur **OK** pour ajouter le schéma sans alias.

     Le schéma est ajouté à la **ajouter un schéma** boîte de dialogue.

7. Dans le **ajouter un schéma** boîte de dialogue, cliquez sur **OK**.

     Le **Structure XML** s’ouvre le volet de tâches.

8. Cliquez sur l’élément de schéma répétitif dans le **Structure XML** volet de tâches pour l’ajouter au document.

     Un <xref:Microsoft.Office.Tools.Word.XMLNodes> contrôle est créé et ajouté au projet.

## <a name="see-also"></a>Voir aussi
- [XMLNodes, contrôle](../vsto/xmlnodes-control.md)
- [Automatiser Word à l’aide d’objets étendus](../vsto/automating-word-by-using-extended-objects.md)
- [Éléments hôtes et la vue d’ensemble des contrôles hôtes](../vsto/host-items-and-host-controls-overview.md)
- [Limitations de programmation des éléments hôtes et contrôles hôtes](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
