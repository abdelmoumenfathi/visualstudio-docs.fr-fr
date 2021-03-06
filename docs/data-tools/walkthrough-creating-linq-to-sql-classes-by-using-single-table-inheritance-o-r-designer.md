---
title: 'Procédure pas à pas : Création de classes LINQ to SQL à l’aide d’un héritage de table individuelle (Concepteur O-R)'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 63bc6328-e0df-4655-9ce3-5ff74dbf69a4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 7bb6562c0eb74f537efb25be031e9c9be46d64b6
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63402689"
---
# <a name="walkthrough-create-linq-to-sql-classes-by-using-single-table-inheritance-or-designer"></a>Procédure pas à pas : Créer de LINQ to SQL classes à l’aide d’héritage à table unique (Concepteur O/R)
Le [des outils LINQ to SQL dans Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) prend en charge l’héritage à table unique tel qu’il est généralement implémenté dans les systèmes relationnels. Cette procédure pas à pas développe les étapes génériques fournies dans le [Comment : Configurer l’héritage à l’aide du Concepteur O/R](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md) rubrique et des données réelles pour illustrer l’utilisation de l’héritage dans le [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

 Au cours de cette procédure pas à pas, vous effectuez les tâches suivantes :

- Créer une table de base de données et ajouter des données.

- Créer une application Windows Forms.

- Ajouter un fichier [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] à un projet.

- Créer de nouvelles classes d'entité.

- Configurer les classes d'entité pour utiliser l'héritage.

- Interroger la classe héritée.

- Afficher les données sur un Windows Form.

## <a name="create-a-table-to-inherit-from"></a>Création d’une table de laquelle hériter
 Pour voir comment fonctionne l’héritage, vous créez un petit `Person` table, utilisez-le comme une classe de base et créez ensuite un `Employee` objet qui en hérite.

### <a name="to-create-a-base-table-to-demonstrate-inheritance"></a>Pour créer une table de base illustrant l'héritage

1. Dans **Explorateur de serveurs** ou **Database Explorer**, avec le bouton droit le **Tables** nœud et cliquez sur **ajouter une nouvelle Table**.

    > [!NOTE]
    > Vous pouvez utiliser la base de données Northwind ou toute autre base de données à laquelle vous pouvez ajouter une table.

2. Dans le **Concepteur de tables**, ajoutez les colonnes suivantes à la table :

    |Nom de la colonne|Type de données|Null autorisé|
    |-----------------|---------------|-----------------|
    |**ID**|**int**|**False**|
    |**Type**|**int**|**True**|
    |**FirstName**|**nvarchar(200)**|**False**|
    |**LastName**|**nvarchar(200)**|**False**|
    |**Manager**|**int**|**True**|

3. Définissez la colonne d'ID comme clé primaire.

4. Enregistrez la table et nommez-la **Personnel**.

## <a name="add-data-to-the-table"></a>Ajouter des données à la table
 Pour pouvoir vérifier si l'héritage est configuré correctement, la table a besoin de données dans chaque classe de l'héritage à table unique.

### <a name="to-add-data-to-the-table"></a>Pour ajouter des données à la table

1. Ouvrez la table dans la vue de données. (Avec le bouton droit le **personne** table **Explorateur de serveurs** ou **Database Explorer** et cliquez sur **afficher les données de Table**.)

2. Copiez les données suivantes dans la table. (Vous pouvez copiez-la et collez-la dans la table en sélectionnant la ligne entière dans le **résultats** volet.)

    ||||||
    |-|-|-|-|-|
    |**ID**|**Type**|**FirstName**|**LastName**|**Manager**|
    |**1**|**1**|**Anne**|**Wallace**|**NULL**|
    |**2**|**1**|**Carlos**|**Grilo**|**NULL**|
    |**3**|**1**|**Yael**|**Peled**|**NULL**|
    |**4**|**2**|**Gatis**|**Ozolins**|**1**|
    |**5**|**2**|**Andreas**|**Hauser**|**1**|
    |**6**|**2**|**Tiffany**|**Phuvasate**|**1**|
    |**7**|**2**|**Alexey**|**Orekhov**|**2**|
    |**8**|**2**|**Michał**|**Poliszkiewicz**|**2**|
    |**9**|**2**|**Tai**|**Yee**|**2**|
    |**10**|**2**|**Fabricio**|**Noriega**|**3**|
    |**11**|**2**|**Mindy**|**Martin**|**3**|
    |**12**|**2**|**Ken**|**Kwok**|**3**|

## <a name="create-a-new-project"></a>Créer un nouveau projet
 Maintenant que vous avez créé la table, créez un nouveau projet pour voir la configuration de l'héritage.

### <a name="to-create-the-new-windows-forms-application"></a>Pour créer la nouvelle application Windows Forms

1. Dans Visual Studio, sur le **fichier** menu, sélectionnez **New** > **projet**.

2. Développez le **Visual C#** ou **Visual Basic** dans le volet gauche, puis sélectionnez **Windows Desktop**.

3. Dans le volet central, sélectionnez le **Windows Forms application** type de projet.

4. Nommez le projet **InheritanceWalkthrough**, puis choisissez **OK**.

     Le projet **InheritanceWalkthrough** est créé et ajouté à l’**Explorateur de solutions**.

## <a name="add-a-linq-to-sql-classes-file-to-the-project"></a>Ajouter un fichier de classes LINQ to SQL au projet

### <a name="to-add-a-linq-to-sql-file-to-the-project"></a>Pour ajouter un fichier LINQ to SQL au projet

1. Dans le menu **Projet** , cliquez sur **Ajouter un nouvel élément**.

2. Cliquez sur le modèle **Classes LINQ to SQL**, puis sur **Ajouter**.

     Le *.dbml* fichier est ajouté au projet et le **Concepteur O/R** s’ouvre.

## <a name="create-the-inheritance-by-using-the-or-designer"></a>Créer l’héritage avec le Concepteur O/R
 Configurez l’héritage en faisant glisser un objet **Héritage** de la **Boîte à outils** vers l’aire de conception.

### <a name="to-create-the-inheritance"></a>Pour créer l'héritage

1. Dans **Explorateur de serveurs** ou **Database Explorer**, accédez à la **personne** table que vous avez créé précédemment.

2. Faites glisser le **personne** table sur le **Concepteur O/R** aire de conception.

3. Faites glisser un deuxième **personne** table sur le **Concepteur O/R** et remplacez son nom par **employé**.

4. Supprimez la propriété **Manager** de l’objet **Personnel**.

5. Supprimez les propriétés **Type**, **ID**, **FirstName** et **LastName** de l’objet **Employé**. (En d’autres termes, supprimez toutes les propriétés à l’exception de **Manager**.)

6. À partir de l’onglet **Concepteur Objet Relationnel** de la **Boîte à outils**, créez un **Héritage** entre les objets **Personnel** et **Employé**. Pour cela, cliquez sur l’élément **Héritage** dans la **Boîte à outils** et relâchez le bouton de la souris. Ensuite, cliquez sur le **employé** objet, puis le **personne** de l’objet dans le **Concepteur O/R**. La flèche sur la ligne d’héritage pointe alors vers le **personne** objet.

7. Cliquez sur la ligne **Héritage** dans l’aire de conception.

8. Affectez à **Propriété de discriminateur** la valeur **Type**.

9. Affectez à la propriété **Valeur de discriminateur de classe dérivée** la valeur **2**.

10. Affectez à la propriété **Valeur de discriminateur de classe de base** la valeur **1**.

11. Affectez à la propriété **Héritage par défaut** la valeur **Personnel**.

12. Générez le projet.

## <a name="query-the-inherited-class-and-display-the-data-on-the-form"></a>Interroger la classe héritée et afficher des données sur le formulaire
 Vous ajoutez maintenant du code au formulaire qui interroge une classe spécifique dans le modèle objet.

### <a name="to-create-a-linq-query-and-display-the-results-on-the-form"></a>Pour créer une requête LINQ et afficher les résultats sur le formulaire

1. Faites glisser une **Zone de liste** sur **Form1**.

2. Double-cliquez sur le formulaire pour créer un gestionnaire d'événements `Form1_Load`.

3. Ajoutez le code suivant au gestionnaire d'événements `Form1_Load` :

    ```vb
    Dim dc As New DataClasses1DataContext
    Dim results = From emp In dc.Persons _
        Where TypeOf emp Is Employee _
        Select emp

    For Each Emp As Employee In results
        ListBox1.Items.Add(Emp.LastName)
    Next
    ```

    ```csharp
    NorthwindDataContext dc = new DataClasses1DataContext();
    var results = from emp in dc.Persons
                  where emp is Employee
                  select emp;

    foreach(Employee Emp in results)
    {
        listBox1.Items.Add(Emp.LastName)
    }
    ```

## <a name="test-the-application"></a>Tester l’application
 Exécutez l’application et vérifiez que les enregistrements affichés dans la zone de liste sont tous des employés (enregistrements qui ont une valeur 2 dans leur colonne **Type**).

### <a name="to-test-the-application"></a>Pour tester l'application

1. Appuyez sur **F5**.

2. Vérifiez que seuls les enregistrements qui ont une valeur 2 dans leur colonne **Type** sont affichés.

3. Fermez le formulaire. (Dans le menu **Déboguer**, cliquez sur **Arrêter le débogage**.)

## <a name="see-also"></a>Voir aussi

- [Outils LINQ to SQL dans Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Procédure pas à pas : Création de LINQ to SQL classes (Concepteur O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [Guide pratique pour affecter des procédures stockées pour effectuer des mises à jour, des insertions et des suppressions (Concepteur O/R)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Guide pratique pour Générer le modèle objet en Visual Basic ouC#](/dotnet/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp)