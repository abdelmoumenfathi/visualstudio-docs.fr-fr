---
title: Créer un contrôle utilisateur Windows Forms qui prend en charge la liaison de données complexe | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data binding, user controls
- data binding, complex
- user controls [Visual Studio], complex data binding
ms.assetid: c8f29c2b-b49b-4618-88aa-33b6105880b5
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0c27ec5be48b37f95068a2be6c8605a97d122d21
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65705007"
---
# <a name="create-a-windows-forms-user-control-that-supports-complex-data-binding"></a>Créer un contrôle utilisateur Windows Forms prenant en charge la liaison de données complexes
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour présenter des données dans des formulaires d’applications Windows, vous pouvez choisir des contrôles existants dans la **Boîte à outils** ou créer des contrôles personnalisés si votre application nécessite des fonctionnalités qui ne sont pas disponibles dans les contrôles standard. Cette procédure pas à pas vous indique comment créer un contrôle qui implémente l'objet <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>. Les contrôles qui implémentent <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> contiennent une propriété `DataSource` et `DataMember` pouvant être liée aux données. Ce type de contrôles est similaire à <xref:System.Windows.Forms.DataGridView> ou <xref:System.Windows.Forms.ListBox>.  
  
 Pour plus d’informations sur la création de contrôles, consultez [développement de contrôles Windows Forms au moment du Design](https://msdn.microsoft.com/library/e5a8e088-7ec8-4fd9-bcb3-9078fd134829).  
  
 Quand vous créez des contrôles utilisables dans des scénarios de liaison de données, vous devez implémenter l’un des attributs de liaison de données suivants :  
  
|Utilisation d’attributs de liaison de données|  
|-----------------------------------|  
|Implémentez <xref:System.ComponentModel.DefaultBindingPropertyAttribute> sur des contrôles simples, comme <xref:System.Windows.Forms.TextBox>, qui affichent une seule colonne (ou propriété) de données. Pour plus d’informations, consultez [créer un contrôle utilisateur Windows Forms qui prend en charge la liaison de données simple](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).|  
|Implémentez <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> sur des contrôles, comme <xref:System.Windows.Forms.DataGridView>, qui affichent des listes (ou tables) de données. (Ce processus est décrit dans cette page de procédure pas à pas.)|  
|Implémentez l'objet <xref:System.ComponentModel.LookupBindingPropertiesAttribute> sur des contrôles, comme <xref:System.Windows.Forms.ComboBox>, qui affichent des listes (ou tables) de données, mais doivent également présenter une seule colonne ou propriété. Pour plus d’informations, consultez [créer un contrôle utilisateur Windows Forms qui prend en charge la liaison de données de recherche](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).|  
  
 Cette procédure pas à pas crée un contrôle complexe affichant les lignes de données d'une table. Cet exemple utilise la table `Customers` de l'exemple de base de données Northwind. Le contrôle utilisateur complexe affiche la table de clients dans un <xref:System.Windows.Forms.DataGridView> dans le contrôle personnalisé.  
  
 Pendant cette procédure pas à pas, vous allez apprendre à :  
  
- Créer un nouveau **Windows Application**.  
  
- Ajouter un nouveau **Contrôle utilisateur** à votre projet.  
  
- Concevoir visuellement le contrôle utilisateur.  
  
- Implémenter l'attribut `ComplexBindingProperty`.  
  
- Créer un jeu de données avec le [Assistant de Configuration de Source de données](https://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f).  
  
- Définir le **clients** table dans le [fenêtre Sources de données](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992) à utiliser le nouveau contrôle complexe.  
  
- Ajouter le nouveau contrôle en le faisant glisser à partir de la **fenêtre Sources de données** sur **Form1**.  
  
## <a name="prerequisites"></a>Prérequis  
 Pour exécuter cette procédure pas à pas, vous avez besoin des éléments suivants :  
  
- avoir accès à l'exemple de base de données Northwind.
  
## <a name="create-a-windows-application"></a>Créer une Application Windows  
 La première étape consiste à créer un **Windows Application**.  
  
#### <a name="to-create-the-new-windows-project"></a>Pour créer un projet Windows  
  
1. Dans Visual Studio, à partir de la **fichier** menu, créez un **projet**.  
  
2. Attribuez le nom **ComplexControlWalkthrough** au projet.  
  
3. Sélectionnez **Windows Application**, puis cliquez sur **OK**. Pour plus d’informations, consultez [les Applications clientes](https://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68).  
  
     Le projet **ComplexControlWalkthrough** est créé et ajouté à l’**Explorateur de solutions**.  
  
## <a name="add-a-user-control-to-the-project"></a>Ajouter un contrôle utilisateur au projet  
 Étant donné que cette procédure pas à pas crée un contrôle complexe pouvant être lié à des données à partir d’un **contrôle utilisateur**, vous devez ajouter un **contrôle utilisateur** élément au projet.  
  
#### <a name="to-add-a-user-control-to-the-project"></a>Pour ajouter un contrôle utilisateur au projet  
  
1. Dans le menu **Projet**, choisissez **Ajouter un contrôle utilisateur**.  
  
2. Tapez **ComplexDataGridView** dans la zone **Nom**, puis cliquez sur **Ajouter**.  
  
     Le contrôle **ComplexDataGridView** est ajouté à l’**Explorateur de solutions** et s’ouvre dans le concepteur.  
  
## <a name="design-the-complexdatagridview-control"></a>Concevoir le contrôle ComplexDataGridView  
 Cette étape ajoute un <xref:System.Windows.Forms.DataGridView> au contrôle utilisateur.  
  
#### <a name="to-design-the-complexdatagridview-control"></a>Pour concevoir le contrôle ComplexDataGridView  
  
- Faites glisser un <xref:System.Windows.Forms.DataGridView> depuis la **Boîte à outils** vers l’aire de conception du contrôle utilisateur.  
  
## <a name="add-the-required-data-binding-attribute"></a>Ajoutez l’attribut de liaison de données requis  
 Pour des contrôles complexes prenant en charge la liaison de données, vous pouvez implémenter l'attribut<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>.  
  
#### <a name="to-implement-the-complexbindingproperties-attribute"></a>Pour implémenter l'attribut ComplexBindingProperties  
  
1. Basculez le contrôle **ComplexDataGridView** en mode Code. (Dans le menu **Affichage**, choisissez **Code**.)  
  
2. Remplacez le code de `ComplexDataGridView` par le code suivant :  
  
     [!code-csharp[VbRaddataDisplaying#4](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/ComplexDataGridView.cs#4)]
     [!code-vb[VbRaddataDisplaying#4](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/ComplexDataGridView.vb#4)]  
  
3. Dans le menu **Générer** , cliquez sur **Générer la solution**.  
  
## <a name="creating-a-data-source-from-your-database"></a>Création d’une source de données à partir de votre base de données  
 Cette étape utilise l’Assistant **Configuration de source de données** pour créer une source de données basée sur la table `Customers` de l’exemple de base de données Northwind. Vous devez avoir accès à l'exemple de base de données Northwind pour créer la connexion. Pour plus d’informations sur la configuration de la base de données Northwind, consultez [bases de données exemple installer SQL Server](../data-tools/install-sql-server-sample-databases.md).  
  
#### <a name="to-create-the-data-source"></a>Pour créer la source de données  
  
1. Dans le menu **Données** , cliquez sur **Afficher les sources de données**.  
  
2. Dans la fenêtre **Sources de données**, sélectionnez **Ajouter une nouvelle source de données** pour démarrer l’Assistant **Configuration de source de données**.  
  
3. Sélectionnez **Base de données** dans la page **Choisir un type de source de données** , puis cliquez sur **Suivant**.  
  
4. Dans la page **Choisir votre connexion de données**, effectuez l’une des opérations suivantes :  
  
    - Si une connexion de données à l’exemple de base de données Northwind est disponible dans la liste déroulante, sélectionnez-la.  
  
    - Sélectionnez **Nouvelle connexion** pour afficher la boîte de dialogue **Ajouter/Modifier la connexion**.  
  
5. Si votre base de données nécessite un mot de passe, sélectionnez l’option pour inclure les données sensibles, puis cliquez sur **Suivant**.  
  
6. Sur le **enregistrer la chaîne de connexion dans le fichier de Configuration de l’Application** , cliquez sur **suivant**.  
  
7. Dans la page **Choisir vos objets de base de données**, développez le nœud **Tables**.  
  
8. Sélectionnez la table `Customers`, puis cliquez sur **Terminer**.  
  
     **NorthwindDataSet** est ajouté à votre projet et la table `Customers` apparaît dans la fenêtre **Sources de données**.  
  
## <a name="set-the-customers-table-to-use-the-complexdatagridview-control"></a>Définir la table Customers pour utiliser le contrôle ComplexDataGridView  
 Dans la fenêtre **Sources de données**, vous pouvez définir le contrôle à créer avant de faire glisser des éléments vers votre formulaire.  
  
#### <a name="to-set-the-customers-table-to-bind-to-the-complexdatagridview-control"></a>Pour définir la table Customers pour qu'elle soit liée au contrôle ComplexDataGridView  
  
1. Ouvrez **Form1** dans le concepteur.  
  
2. Développez le nœud **Customers** dans la fenêtre **Sources de données**.  
  
3. Cliquez sur la flèche déroulante du nœud **Customers** et choisissez **Personnaliser**.  
  
4. Sélectionnez **ComplexDataGridView** dans la liste des **Contrôles associés** de la boîte de dialogue **Options de personnalisation de l’interface utilisateur de données**.  
  
5. Cliquez sur la flèche déroulante de la table `Customers` et choisissez **ComplexDataGridView** dans la liste de contrôles.  
  
## <a name="addcontrols-to-the-form"></a>Addcontrols au formulaire  
 Pour créer des contrôles liés aux données, vous pouvez faire glisser des éléments depuis la fenêtre **Sources de données** vers votre formulaire.  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>Pour créer des contrôlés liés aux données dans le formulaire  
  
- Faites glisser le **clients** nœud à partir de la **des Sources de données** fenêtre vers le formulaire. Vérifiez que le **ComplexDataGridView** contrôle est utilisé pour afficher les données de la table.  
  
## <a name="running-the-application"></a>Exécution de l’application  
  
#### <a name="to-run-the-application"></a>Pour exécuter l’application  
  
- Appuyez sur F5 pour exécuter l'application.  
  
## <a name="next-steps"></a>Étapes suivantes  
 Selon les spécifications de votre application, vous pouvez exécuter différentes étapes après la création d'un contrôle prenant en charge la liaison de données. Les étapes ultérieures sont habituellement celles-ci :  
  
- Positionnement de vos contrôles personnalisés dans une bibliothèque de contrôles pour pouvoir les réutiliser dans d'autres applications.  
  
- Création de contrôles prenant en charge les scénarios de recherche. Pour plus d’informations, consultez [créer un contrôle utilisateur Windows Forms qui prend en charge la liaison de données de recherche](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Lier des contrôles Windows Forms à des données dans Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Définir le contrôle à créer lors du déplacement de la fenêtre Sources de données](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)   
 [Contrôles Windows Forms](https://msdn.microsoft.com/library/f050de8f-4ebd-4042-94b8-edf9a1dbd52a)
