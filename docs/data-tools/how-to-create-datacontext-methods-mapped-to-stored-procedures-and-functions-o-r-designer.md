---
title: 'Procédure : créer des méthodes DataContext mappées à des procédures stockées et à des fonctions (Concepteur O-R)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: dc2b1c25f9b4cf9bc777eefd0c95985a534799b5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62566506"
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>Procédure : créer des méthodes DataContext mappées à des procédures stockées et à des fonctions (Concepteur O/R)

Vous pouvez ajouter des procédures stockées et des fonctions pour le **Concepteur O/R** comme <xref:System.Data.Linq.DataContext> méthodes. En appelant la méthode pour passer les paramètres requis, la procédure stockée ou fonction est exécutée sur la base de données et retourne les données dans le type de retour de la méthode <xref:System.Data.Linq.DataContext>. Pour plus d’informations sur <xref:System.Data.Linq.DataContext> méthodes, consultez [DataContext, méthodes (Concepteur O/R)](../data-tools/datacontext-methods-o-r-designer.md).

> [!NOTE]
> Vous pouvez également utiliser des procédures stockées pour remplacer la valeur par défaut [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] comportement d’exécution qui effectue des insertions, mises à jour et des suppressions lorsque les modifications sont enregistrées à partir des classes d’entité dans une base de données. Pour plus d'informations, voir [Procédure : affecter des procédures stockées pour effectuer des mises à jour, des insertions et des suppressions (Concepteur O/R)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

## <a name="create-datacontext-methods"></a>Créer des méthodes DataContext

Vous pouvez créer <xref:System.Data.Linq.DataContext> méthodes en faisant glisser des procédures stockées ou fonctions de <strong>Explorateur de serveurs ou ** l’Explorateur de base de données</strong> sur le **Concepteur O/R**.

> [!NOTE]
> Le type de retour de généré <xref:System.Data.Linq.DataContext> méthode diffère selon l’endroit où vous placez la procédure stockée ou fonction sur le **Concepteur O/R**. Le déplacement direct des éléments vers une classe d'entité existante crée une méthode <xref:System.Data.Linq.DataContext> avec le type de retour de la classe d'entité. Suppression d’éléments dans une zone vide de la **Concepteur O/R** crée un <xref:System.Data.Linq.DataContext> méthode qui retourne un type généré automatiquement. Vous pouvez modifier le type de retour d’une méthode <xref:System.Data.Linq.DataContext> après l’avoir ajoutée au volet **Méthodes**. Pour inspecter ou modifier le type de retour d’une méthode <xref:System.Data.Linq.DataContext>, sélectionnez-la et inspectez la propriété **Type de retour** dans la fenêtre **Propriétés**. Pour plus d'informations, voir [Procédure : modifier le type de retour d’une méthode DataContext (Concepteur O/R)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>Pour créer des méthodes DataContext qui retournent automatiquement les types générés

1. Dans **Explorateur de serveurs** ou **Database Explorer**, développez le **Stored Procedures** nœud de la base de données avec laquelle vous travaillez.

2. Localisez la procédure stockée souhaitée et faites-le glisser sur une zone vide de la **Concepteur O/R**.

     La méthode <xref:System.Data.Linq.DataContext> est créée avec un type de retour généré automatiquement et apparaît dans le volet **Méthodes**.

### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>Pour créer des méthodes DataContext qui ont le type de retour d'une classe d'entité

1. Dans **Explorateur de serveurs** ou **Database Explorer**, développez le **Stored Procedures** nœud de la base de données avec laquelle vous travaillez.

2. Localisez la procédure stockée requise et faites-la glisser vers une classe d’entité existante dans le **Concepteur O/R**.

     La méthode <xref:System.Data.Linq.DataContext> est créée avec le type de retour de la classe d’entité sélectionnée et apparaît dans le volet **Méthodes**.

> [!NOTE]
> Pour plus d’informations sur la modification du type de retour d’existant <xref:System.Data.Linq.DataContext> méthodes, consultez [Comment : modifier le type de retour d’une méthode DataContext (Concepteur O/R)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

## <a name="see-also"></a>Voir aussi

- [Outils LINQ to SQL dans Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [DataContext, méthodes (Concepteur O/R)](../data-tools/datacontext-methods-o-r-designer.md)
- [Procédure pas à pas : Création de LINQ aux classes SQL](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Introduction à LINQ en Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)
- [LINQ en C#](/dotnet/csharp/linq/linq-in-csharp)