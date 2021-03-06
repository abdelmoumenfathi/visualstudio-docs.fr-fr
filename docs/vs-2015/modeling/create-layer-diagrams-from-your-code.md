---
title: Créer des diagrammes de couche à partir de votre code | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- architecture, layer diagrams
- layer diagrams
- diagrams - modeling, layer
- constraints, architectural
ms.assetid: 58c3ea71-2dbc-4963-bf82-40f1924cf973
caps.latest.revision: 64
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8fd8188ef0efbe540e086ca6ce284a49b71444ed
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63433379"
---
# <a name="create-layer-diagrams-from-your-code"></a>Créer des diagrammes de couche à partir de votre code
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pour visualiser l’architecture de haut niveau et logique de votre système logiciel, créez un *diagramme de couche* dans Visual Studio. Pour vous assurer que votre code demeure conforme à cette conception, validez-le avec un diagramme de couche. Vous pouvez créer des diagrammes de couche pour les projets Visual C# .NET et Visual Basic .NET. Pour connaître les versions de Visual Studio prennent en charge cette fonctionnalité, consultez [versions prises en charge pour l’architecture et les outils de modélisation](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)  
  
 ![Créer un diagramme de couche](../modeling/media/layerdiagramvisualizecode.png "LayerDiagramVisualizeCode")  
  
 Un diagramme de couche vous permet d’organiser les éléments de solution Visual Studio en groupes logiques et abstraits appelés *couches*. Vous pouvez utiliser les couches pour décrire des tâches importantes que ces artefacts effectuent ou bien les principaux composants du système. Chaque couche peut contenir d'autres couches qui décrivent des tâches plus détaillées. Vous pouvez également spécifier prévues ou existantes *dépendances* entre les couches. Ces dépendances, qui sont représentées par des flèches, indiquent quels couches peuvent utiliser ou utilisent actuellement la fonctionnalité représentée par d'autres couches. Pour maintenir le contrôle architecturel du code, affichez les dépendances prévues sur le diagramme, puis validez le code par rapport au diagramme.  
  
## <a name="CreateDiagram"></a> Créer un diagramme de couche  
 Avant de créer un diagramme de couche, vérifiez que votre solution a un projet de modélisation. Consultez [diagrammes et projets de modélisation UML créer](../modeling/create-uml-modeling-projects-and-diagrams.md).  
  
> [!IMPORTANT]
> Vous ne pouvez pas ajouter, glisser-déposer ni copier un diagramme de couche existant d'un projet de modélisation à un autre, ou bien vers un autre emplacement de la solution. Cela permet de conserver les références du diagramme d'origine, même si vous modifiez le diagramme. Cela empêche également un mauvais fonctionnement de la validation de couche et pourra provoquer d’autres problèmes, tels que des éléments manquants ou autre erreurs lorsque vous essayez d’ouvrir le diagramme.  
>   
> Ajoutez au lieu de cela un nouveau diagramme de couche au projet de modélisation. Copiez les éléments depuis le diagramme source vers le nouveau diagramme. Enregistrez le projet de modélisation et le nouveau diagramme de couche.  
  
#### <a name="to-add-a-new-layer-diagram-to-a-modeling-project"></a>Pour ajouter un nouveau diagramme de couche à un projet de modélisation  
  
1. Sur le **Architecture** menu, choisissez **nouveau UML ou diagramme de couche**.  
  
2. Sous **modèles**, choisissez **diagramme de couche**.  
  
3. Nommez le diagramme.  
  
4. Dans **ajouter au projet de modélisation**, recherchez et sélectionnez un projet de modélisation existant dans votre solution.  
  
     ou  
  
     Choisissez **créer un nouveau projet de modélisation** pour ajouter un nouveau projet de modélisation à la solution.  
  
    > [!NOTE]
    > Le diagramme de couche doit être présent dans un projet de modélisation. Toutefois, vous pouvez le lier à des éléments situés n'importe où dans la solution.  
  
5. Veillez à enregistrer à la fois le projet de modélisation et le diagramme de couche.  
  
## <a name="CreateLayers"></a> Créer des couches à partir d’artefacts  
 Vous pouvez créer des couches à partir d'éléments de solution Visual Studio, tels que des projets, des fichiers de code, des espaces de noms, des classes et des méthodes. Cela crée automatiquement des liens entre ces couches et les éléments, les incluant dans le processus de validation de couche.  
  
 Afin de pouvoir associer une couche à des caractéristiques ou des plans, vous pouvez également lier des couches à des éléments qui ne prennent pas en charge la validation, tels que des documents Word ou des présentations PowerPoint. Vous pouvez également lier des couches à des fichiers dans des projets qui sont partagés sur plusieurs applications, mais le processus de validation n’inclut pas ces couches qui s’affichent avec des noms génériques tels que « Couche 1 » et « Couche 2 ».  
  
 Pour voir si un élément lié prend en charge la validation, ouvrez **Explorateur de couches** et examinez le **prend en charge la Validation** propriété de l’élément. Consultez [la gestion des liens vers les artefacts](#Managing).  
  
|**To**|**Procédez comme suit**|  
|------------|----------------------------|  
|Créer une couche pour un artefact unique|<ol><li>Faites glisser l'élément sur le diagramme de couche à partir de ces sources :<br /><br /> <ul><li>**Explorateur de solutions**<br /><br />         Par exemple, vous pouvez faire glisser des fichiers ou des projets.</li><li>Cartes de code<br /><br />         Consultez [mapper les dépendances dans vos solutions](../modeling/map-dependencies-across-your-solutions.md) et [les cartes de code de l’utiliser pour déboguer vos applications](../modeling/use-code-maps-to-debug-your-applications.md).</li><li>**Affichage de classes** ou **Explorateur d’objets**</li></ul><br />     Une couche s’affiche sur le diagramme et est liée à l’artefact.</li><li>Renommez la couche pour refléter les responsabilités du code ou des artefacts associés.</li></ol> **Important :**  Faire glisser des fichiers binaires vers le diagramme de couche n'ajoute pas automatiquement leurs références au projet de modélisation. Vous devez ajouter manuellement au projet de modélisation les fichiers binaires que vous voulez valider. **Pour ajouter des fichiers binaires au projet de modélisation** <ol><li>Dans **l’Explorateur de solutions**, ouvrez le menu contextuel du projet de modélisation, puis choisissez **ajouter un élément existant**.</li><li>Dans le **ajouter un élément existant** boîte de dialogue, recherchez les fichiers binaires, sélectionnez-les, puis choisissez **OK**.     Les fichiers binaires s'affichent dans le projet de modélisation.</li><li>Dans **l’Explorateur de solutions**, choisissez un fichier binaire que vous avez ajouté, puis appuyez sur **F4** pour ouvrir le **propriétés** fenêtre.</li><li>Sur chaque fichier binaire, définissez la **Action de génération** propriété **Validate**.</li></ol>|  
|Créer une couche unique pour tous les artefacts sélectionnés|Faites glisser en même temps tous les artefacts vers le diagramme de couche.<br /><br /> Une couche qui est liée à tous les artefacts s’affiche sur le diagramme.|  
|Créer une couche pour chaque artefact sélectionné|Maintenez la **MAJ** enfoncée pendant que vous faites glisser en même temps tous les artefacts vers le diagramme de couche. **Remarque :**  Si vous utilisez le **MAJ** clé pour sélectionner une plage d’éléments, relâchez la touche après avoir sélectionné les artefacts. Appuyez de nouveau sur celle-ci et maintenez-la enfoncée lorsque vous faites glisser les artefacts vers le diagramme. <br /><br /> Une couche s'affiche sur le diagramme pour chaque artefact, auquel elle est liée.|  
|Ajouter un artefact à une couche|Faites glisser l'artefact vers la couche.|  
|Créer une couche non liée|Dans le **boîte à outils**, développez le **diagramme de couche** section et faites glisser un **couche** au diagramme de couche.<br /><br /> Pour ajouter plusieurs couches, double-cliquez sur l'outil. Lorsque vous avez terminé, choisissez le **pointeur** outil ou appuyez sur la **ÉCHAP** clé.<br /><br /> ou<br /><br /> Ouvrez le menu contextuel pour le diagramme de couche, choisissez **ajouter**, puis choisissez **couche**.|  
|Créer des couches imbriquées|Faites glisser une couche existante sur une autre couche.<br /><br /> ou<br /><br /> Ouvrez le menu contextuel pour une couche, choisissez **ajouter**, puis choisissez **couche**.|  
|Créer une nouvelle couche qui contient deux ou plusieurs couches existantes|Sélectionnez les couches, ouvrez le menu contextuel pour votre sélection, puis **groupe**.|  
|Modifier la couleur d'une couche|Définissez ses **couleur** couleur dans la propriété que vous souhaitez.|  
|Spécifier que les artefacts associés à une couche ne doivent pas appartenir aux espaces de noms spécifiés|Tapez les espaces de noms dans la couche **interdit les espaces de noms** propriété. Utilisez un point-virgule (**;**) pour séparer les espaces de noms.|  
|Spécifier que les artefacts associés à une couche ne peuvent pas dépendre des espaces de noms spécifiés|Tapez les espaces de noms dans la couche **interdit les dépendances de Namespace** propriété. Utilisez un point-virgule (**;**) pour séparer les espaces de noms.|  
|Spécifier que les artefacts associés à une couche doivent appartenir à un des espaces de noms spécifiés|Tapez l’espace de noms dans la couche **espaces de noms requis** propriété. Utilisez un point-virgule (**;**) pour séparer les espaces de noms.|  
  
 Le nombre indiqué sur une couche représente le nombre d’artefacts liés à cette couche. Toutefois, à la lecture de ce nombre, souvenez-vous de ce qui suit :  
  
- Si une couche est liée à un artefact contenant d'autres artefacts, mais n'est pas directement liée à ces autres artefacts, le nombre représentera uniquement les artefacts auxquels elle est directement liée. Toutefois, les autres artefacts sont inclus dans l'analyse pendant la validation de couche.  
  
     Par exemple, si une couche est liée à un espace de noms unique, le nombre d'artefacts liés est égal à 1, même si l'espace de noms contient des classes. Si la couche a également des liens vers chaque classe de l'espace de noms, le nombre comprendra les classes liées.  
  
- Si une couche contient d'autres couches liées à des artefacts, la couche du conteneur est également liée à ces artefacts, même si le nombre indiqué sur la couche du conteneur ne comprend pas ces artefacts.  
  
## <a name="Managing"></a> Gérer les liens entre les couches et les artefacts  
  
1. Sur le diagramme de couche, ouvrez le menu contextuel de la couche, puis choisissez **afficher les liens**.  
  
     **Explorateur de couches** affiche les liens d’artefact pour la couche sélectionnée.  
  
2. Utilisez les tâches suivantes pour gérer ces liens :  
  
|**To**|**Dans l’Explorateur de couches**|  
|------------|---------------------------|  
|Supprimer le lien entre la couche et un artefact|Ouvrez le menu contextuel pour le lien d’artefact, puis choisissez **supprimer**.|  
|Déplacer le lien d'une couche vers une autre|Faites glisser le lien d'artefact vers une couche existante sur le diagramme.<br /><br /> ou<br /><br /> 1.  Ouvrez le menu contextuel pour le lien d’artefact, puis choisissez **couper**.<br />2.  Sur le diagramme de couche, ouvrez le menu contextuel de la couche, puis choisissez **coller**.|  
|Copier le lien d'une couche vers une autre|1.  Ouvrez le menu contextuel pour le lien d’artefact, puis choisissez **copie**.<br />2.  Sur le diagramme de couche, ouvrez le menu contextuel de la couche, puis choisissez **coller**.|  
|Créer une nouvelle couche à partir d’un lien d’artefact existant|Faites glisser le lien d’artefact vers une zone vide sur le diagramme.|  
|Vérifiez qu’un artefact lié prend en charge la validation par rapport au diagramme de couche.|Examinez le **prend en charge la Validation** colonne pour le lien d’artefact.|  
  
## <a name="Discovering"></a> Procéder à la rétroconception des dépendances existantes  
 Une dépendance existe chaque fois qu'un artefact associé à une couche comporte une référence à un artefact associé à une autre couche. Par exemple, une classe dans une couche déclare une variable qui a une classe dans une autre couche. Vous pouvez effectuer une ingénierie à rebours des dépendances existantes pour les artefacts liés aux couches sur le diagramme.  
  
> [!NOTE]
> Les dépendances ne peuvent pas faire l'objet d'une ingénierie à rebours pour certains genres d'artefacts. Par exemple, aucune dépendance ne fera l'objet d'une ingénierie à rebours depuis ou vers une couche qui est liée à un fichier texte. Pour voir les artefacts ayant des dépendances que vous pouvez procéder à la rétroconception, ouvrez le menu contextuel pour une ou plusieurs couches, puis choisissez **afficher les liens**. Dans **Explorateur de couches**, examinez le **prend en charge la Validation** colonne. Dépendances ne sera pas à rebours pour les artefacts pour lesquels cette colonne affiche **False**.  
  
- Sélectionnez une ou plusieurs couches, ouvrez le menu contextuel pour une couche sélectionnée, puis **générer des dépendances**.  
  
  En général, des dépendances qui ne devraient pas exister s'affichent. Vous pouvez modifier ces dépendances pour les ajuster à la conception prévue.  
  
## <a name="EditDependencies"></a> Modifier les couches et les dépendances pour afficher la conception prévue  
 Pour décrire les modifications que vous envisagez d'apporter à votre système ou l'architecture attendue, modifiez le diagramme de couche :  
  
|**To**|**Effectuez ces étapes**|  
|------------|-----------------------------|  
|Changer ou restreindre la direction d'une dépendance|Définissez ses **Direction** propriété.|  
|Créer de nouvelles dépendances|Utilisez le **dépendance** et **dépendance bidirectionnelle** outils.<br /><br /> Pour dessiner plusieurs dépendances, double-cliquez sur l'outil. Lorsque vous avez terminé, choisissez le **pointeur** outil ou appuyez sur la **ÉCHAP** clé.|  
|Spécifier que les artefacts associés à une couche ne peuvent pas dépendre des espaces de noms spécifiés|Tapez les espaces de noms dans la couche **interdit les dépendances de Namespace** propriété. Utilisez un point-virgule (**;**) pour séparer les espaces de noms.|  
|Spécifier que les artefacts associés à une couche ne doivent pas appartenir aux espaces de noms spécifiés|Tapez les espaces de noms dans la couche **interdit les espaces de noms** propriété. Utilisez un point-virgule (**;**) pour séparer les espaces de noms.|  
|Spécifier que les artefacts associés à une couche doivent appartenir à un des espaces de noms spécifiés|Tapez l’espace de noms dans la couche **espaces de noms requis** propriété. Utilisez un point-virgule (**;**) pour séparer les espaces de noms.|  
  
## <a name="EditLayout"></a> Modifier l’apparaissent des éléments dans le diagramme  
 Vous pouvez modifier la taille, la forme, la couleur et la position des couches ou de la couleur des dépendances en modifiant leurs propriétés.  
  
## <a name="Codemaps"></a> Découvrir des modèles et des dépendances sur une carte de code  
 Lors de la création de diagrammes de couche, vous pouvez également créer **cartes de code**. Ces diagrammes peuvent vous aider à découvrir des modèles et des dépendances quand vous explorez le code. Utilisez l'Explorateur de solutions, l'Affichage de classes ou l'Explorateur d'objets pour explorer les assemblys, les espaces de noms et les classes, qui correspondent souvent à des couches existantes. Pour plus d'informations sur les cartes de code, consultez :  
  
- [Mapper les dépendances à travers vos solutions](../modeling/map-dependencies-across-your-solutions.md)  
  
- [Utiliser des cartes de code pour déboguer vos applications](../modeling/use-code-maps-to-debug-your-applications.md)  
  
- [Rechercher des problèmes potentiels à l’aide des analyseurs de carte du code](../modeling/find-potential-problems-using-code-map-analyzers.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Vidéo Channel 9 : Concevoir et valider votre architecture à l’aide de diagrammes de couche](http://go.microsoft.com/fwlink/?LinkID=252073)   
 [Diagrammes de couche : Référence](../modeling/layer-diagrams-reference.md)   
 [Diagrammes de couche : Instructions](../modeling/layer-diagrams-guidelines.md)   
 [Valider du code avec des diagrammes de couche](../modeling/validate-code-with-layer-diagrams.md)   
 [Visualiser du code](../modeling/visualize-code.md)