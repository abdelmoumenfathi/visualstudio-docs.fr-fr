---
title: Informations de référence sur le langage DGML (Directed Graph Markup Language)
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b473dc706cd7183835c5d84091fb53e45337c013
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62834215"
---
# <a name="directed-graph-markup-language-dgml-reference"></a>Informations de référence sur le langage DGML (Directed Graph Markup Language)

Le langage DGML (Directed Graph Markup Language) décrit les informations utilisées pour la visualisation et l'analyse de complexité. Il s'agit du format utilisé pour faire persister des cartes de code dans Visual Studio. Il utilise le langage XML simple pour décrire des graphiques orientés à la fois cycliques et acycliques. Un graphique orienté est un ensemble de nœuds reliés par des liens (ou bords). Les nœuds et les liens peuvent être utilisés pour représenter des structures interconnectées, telles que les éléments d'un projet logiciel.

Notez que certaines versions de Visual Studio prend en charge uniquement un sous-ensemble de fonctionnalités DGML, consultez [versions prises en charge pour l’architecture et les outils de modélisation](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

> [!NOTE]
> Lorsque vous modifiez un fichier .dgml, IntelliSense vous aide à identifier les attributs qui sont disponibles pour chaque élément, ainsi que leurs valeurs. Pour spécifier la couleur dans un attribut, utilisez le nom des couleurs courantes (« Bleu », par exemple) ou des valeurs hexadécimales ARVB (« #ffa0b1c3 », par exemple). Le langage DGML utilise un sous-ensemble réduit de formats de définition de couleur WPF (Windows Presentation Foundation). Pour plus d’informations, consultez [couleurs classe](http://go.microsoft.com/fwlink/?LinkId=182345).

## <a name="DGML"></a> Syntaxe du langage DGML

Le tableau suivant décrit les types d'éléments utilisés en langage DGML :

- `<DirectedGraph></DirectedGraph>`

   Cet élément est l'élément racine du document de carte de code (.dgml). Tous les autres éléments DGML s'inscrivent dans la portée de cet élément.

   La liste suivante décrit des attributs facultatifs que vous pouvez inclure :

   `Background` : couleur de l'arrière-plan de la carte.

   `BackgroundImage` : emplacement du fichier image à utiliser en tant qu'arrière-plan de la carte.

   `GraphDirection` : quand la carte se présente sous forme d'arborescence (`Sugiyama`), disposez les nœuds de sorte que la plupart des liens suivent la direction spécifiée : `TopToBottom`, `BottomToTop`, `LeftToRight` ou `RightToLeft`. Consultez [modifier la disposition de la carte](../modeling/browse-and-rearrange-code-maps.md#Selecting).

   `Layout` : affectez à la carte les dispositions suivantes : `None`, `Sugiyama` (présentation sous forme d'arborescence), `ForceDirected` (clusters rapides) ou `DependencyMatrix`. Consultez [modifier la disposition de la carte](../modeling/browse-and-rearrange-code-maps.md#Selecting).

   `NeighborhoodDistance`  : quand la carte se présente sous forme d'arborescence ou de clusters rapides, seuls les nœuds qui possèdent un nombre spécifié de liens (de 1 à 7) éloignés des nœuds sélectionnés s'affichent. Consultez [modifier la disposition de la carte](../modeling/browse-and-rearrange-code-maps.md#Selecting).

   Exemple :

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <DirectedGraph Title="DrivingTest" Background="Blue" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
     <Nodes>
        ...
     </Nodes>
     <Links>
        ...
     </Links>
     <Categories>
        ...
     </Categories>
     <Properties>
        ...
     </Properties>
  </DirectedGraph>
  ```

- `<Nodes></Nodes>`

   Cet élément facultatif contient une liste d'éléments `<Node/>` qui définissent des nœuds sur la carte. Pour plus d'informations, consultez l'élément `<Node/>`.

  > [!NOTE]
  > Quand vous faites référence à un nœud non défini dans un élément `<Link/>`, la carte crée automatiquement un élément `<Node/>`.

   Exemple :

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
     <Nodes>
        <Node ... />
     </Nodes>
     <Links>
        <Link ... />
     </Links>
  </DirectedGraph>
  ```

- `<Node/>`

   Cet élément définit un nœud unique. Il figure dans la liste des éléments `<Nodes><Nodes/>`.

   Cet élément doit inclure les attributs suivants :

   `Id` - Nom unique du nœud et valeur par défaut de l'attribut `Label`, lorsqu'aucun attribut `Label` séparé n'est spécifié. Ce nom doit correspondre à l'attribut `Source` ou `Target` du lien qui y fait référence.

   La liste suivante décrit certains des attributs facultatifs que vous pouvez inclure :

   `Label` -Nom complet du nœud.

   Attributs Style. Consultez [Personnaliser des cartes de code en modifiant les fichiers DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).

   `Category` - Nom d'une catégorie qui identifie les éléments qui partagent cet attribut. Pour plus d'informations, consultez l'élément `<Category/>`.

   `Property` - Nom d'une propriété qui identifie des éléments qui ont la même valeur de propriété. Pour plus d'informations, consultez l'élément `<Property/>`.

   `Group` - Si le nœud contient d'autres nœuds, affectez à cet attribut la valeur `Expanded` ou `Collapsed` pour respectivement en afficher ou en masquer le contenu. Un élément `<Link/>` doit inclure l'attribut `Category="Contains"` et spécifier le nœud parent en tant que nœud source et le nœud enfant en tant que nœud cible. Consultez [regrouper des éléments de code](../modeling/customize-code-maps-by-editing-the-dgml-files.md#OrganizeNodes).

   `Visibility` - Affectez à cet attribut la valeur `Visible`, `Hidden` ou `Collapsed`. Utilise `System.Windows.Visibility`. Consultez [masquer ou afficher les nœuds et les liens](../modeling/browse-and-rearrange-code-maps.md#HidingShowing).

   `Reference` - Définissez cet attribut pour le lier à un document ou une URL. Consultez [lier des documents ou des URL aux éléments de code et aux liens](../modeling/customize-code-maps-by-editing-the-dgml-files.md#AddReferences).

   Exemple :

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
     <Nodes>
        <Node Id="Driver" Label="Student" Category="Person" />
        <Node Id="Passenger" Label="Instructor" Category="Person" />
        <Node Id="Car" Label="Car" Category="Automobile" />
        <Node Id="Truck" Label="Truck" Category="Automobile" />
     </Nodes>
     <Links>
        <Link ... />
     </Links>
     <Categories>
        <Category Id="Person" Background="Orange" />
        <Category Id="Automobile" Background="Yellow"/>
     </Categories>
  </DirectedGraph>
  ```

- `<Links></Links>`

   Cet élément contient la liste des éléments `<Link>` qui définissent des liens entre des nœuds. Pour plus d'informations, consultez l'élément `<Link/>`.

   Exemple :

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
     <Links>
        <Link ... />
     </Links>
  </DirectedGraph>
  ```

- `<Link/>`

   Cet élément définit un lien unique qui relie un nœud source à un nœud cible. Il figure dans la liste des éléments `<Links></Links>`.

  > [!NOTE]
  > Si cet élément fait référence à un nœud non défini, le document de la carte crée automatiquement un nœud qui possède les attributs spécifiés, le cas échéant.

   Cet élément doit inclure les attributs suivants :

   `Source` - Nœud source du lien.

   `Target` - Nœud cible du lien.

   La liste suivante décrit certains des attributs facultatifs que vous pouvez inclure :

   `Label` - Nom complet du lien.

   Attributs Style. Consultez [Personnaliser des cartes de code en modifiant les fichiers DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).

   `Category` - Nom d'une catégorie qui identifie les éléments qui partagent cet attribut. Pour plus d'informations, consultez l'élément `<Category/>`.

   `Property` - Nom d'une propriété qui identifie des éléments qui ont la même valeur de propriété. Pour plus d'informations, consultez l'élément `<Property/>`.

   Exemple :

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
     <Nodes>
        <Node Id="Driver" Label="Student" Category="Person" />
        <Node Id="Passenger" Label="Instructor" Category="Person" />
        <Node Id="Car" Label="Car" Category="Automobile" />
        <Node Id="Truck" Label="Truck" Category="Automobile" />
     </Nodes>
     <Links>
        <Category Id="Person" Background="Orange" />
        <Category Id="Automobile" Background="Yellow"/>
        <Link Source="Driver" Target="Car" Label="Passed" Stroke="Black" Background="Green" Category="PassedTest" />
        <Link Source="Driver" Target="Truck" Label="Failed" Stroke="Black" Background="Red" Category="PassedTest" />
     </Links>
  </DirectedGraph>
  ```

- `<Categories></Categories>`

   Cet élément contient la liste des éléments `<Category/>`. Pour plus d'informations, consultez l'élément `<Category/>`.

   Exemple :

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
     <Categories>
         <Category ... />
     </Categories>
  </DirectedGraph>
  ```

- `<Category/>`

   Cet élément définit un attribut `Category` qui permet d'identifier les éléments qui partagent cet attribut. Un attribut `Category` peut être utilisé pour organiser des éléments de carte, proposer des attributs partagés par héritage ou définir d'autres métadonnées.

   Cet élément doit inclure les attributs suivants :

   `Id` - Nom unique de la catégorie et valeur par défaut de l'attribut `Label`, lorsqu'aucun attribut `Label` séparé n'est spécifié.

   La liste suivante décrit certains des attributs facultatifs que vous pouvez inclure :

   `Label` - Nom convivial de la catégorie.

   `BasedOn` - Catégorie parente dont le `<Category/>` de l'élément actuel hérite.

   Dans l'exemple donné pour cet élément, la catégorie `FailedTest` hérite de son attribut `Stroke` à partir de la catégorie `PassedTest`. Consultez « pour créer des catégories hiérarchiques » dans [cartes de code de la personnaliser en modifiant les fichiers DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).

   Les catégories proposent également un comportement de modèle de base qui contrôle l'apparence des nœuds et des liens lorsqu'ils s'affichent sur une carte. Consultez [Personnaliser des cartes de code en modifiant les fichiers DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).

   Exemple :

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
     <Nodes>
        <Node Id="Driver" Label="Driver" Category="Person" />
        <Node Id="Car" Label="Car" Category="Automobile" />
        <Node Id="Truck" Label="Truck" Category="Automobile" />
        <Node Id="Passenger" Category="Person" />
     </Nodes>
     <Links>
        <Link Source="Driver" Target="Car" Label="Passed" Category="PassedTest" />
        <Link Source="Driver" Target="Truck" Label="Failed" Category="FailedTest" />
     </Links>
     <Categories>
        <Category Id="Person" Background="Orange" />
        <Category Id="Automobile" Background="Yellow"/>
        <Category Id="PassedTest" Label="Passed" Stroke="Black" Background="Green" />
        <Category Id="FailedTest" Label="Failed" BasedOn="PassedTest" Background="Red" />
     </Categories>
  </DirectedGraph>
  ```

- `<Properties></Properties>`

   Cet élément contient la liste des éléments `<Property/>`. Pour plus d'informations, consultez l'élément `<Property/>`.

   Exemple :

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
     <Properties>
         <Property ... />
     </Properties>
  </DirectedGraph>
  ```

- `<Property/>`

   Cet élément définit un attribut `Property` que vous pouvez utiliser pour assigner une valeur à tout attribut ou élément DGML, y compris des catégories et autres propriétés.

   Cet élément doit inclure les attributs suivants :

  - `Id` - Nom unique de la propriété et valeur par défaut de l'attribut `Label`, lorsqu'aucun attribut `Label` séparé n'est spécifié.

  - `DataType` - Type de données stockées par la propriété.

    Si vous souhaitez que la propriété s’affiche dans le **propriétés** fenêtre, utilisez le `Label` propriété pour spécifier le nom d’affichage de la propriété.

    Consultez [attribuer des catégories aux éléments de code et aux liens](../modeling/customize-code-maps-by-editing-the-dgml-files.md#AssignCategories).

    Exemple :

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <DirectedGraph Title="DrivingTest" xmlns="http://schemas.microsoft.com/vs/2009/dgml">
     <Nodes>
        <Node Id="Driver" Label="Driver" Category="Person" DrivingAge="18"/>
        <Node Id="Car" Label="Car" Category="Automobile" />
        <Node Id="Truck" Label="Truck" Category="Automobile" />
        <Node Id="Passenger" Category="Person" />
     </Nodes>
     <Links>
        <Link Source="Driver" Target="Car" Label="Passed" Category="PassedTest" />
        <Link Source="Driver" Target="Truck" Label="Failed" Category="FailedTest" />
     </Links>
     <Categories>
        <Category Id="Person" Background="Orange" />
        <Category Id="Automobile" Background="Yellow"/>
        <Category Id="PassedTest" Label="Passed" Stroke="Black" Background="Green" />
        <Category Id="FailedTest" Label="Failed" BasedOn="PassedTest" Background="Red" />
     </Categories>
     <Properties>
         <Property Id="DrivingAge" Label="Driving Age" DataType="System.Int32" />
     </Properties>
  </DirectedGraph>
  ```

### <a name="AddAlias"></a> Alias pour les chemins d’accès fréquemment utilisés

Lorsque vous remplacez des chemins d'accès fréquemment utilisés par des alias, vous réduisez la taille du fichier .dgml, ainsi que la durée nécessaire au téléchargement et à l'enregistrement du fichier. Pour créer un alias, ajoutez une section `<Paths></Paths>` à la fin du fichier .dgml. Dans cette section, ajoutez un élément `<Path/>` pour définir un alias pour le chemin d'accès :

```xml
<Paths>
   <Path Id="MyPathAlias" Value="C:\...\..." />
</Paths>
```

Pour référencer l’alias à partir d’un élément dans le fichier .dgml, mettez le `Id` de la \<chemin d’accès / > élément par un signe dollar ($) et des parenthèses (()) :

```xml
<Nodes>
   <Node Id="MyNode" Reference="$(MyPathAlias)MyDocument.txt" />
</Nodes>
<Properties>
   <Property Id="Reference" Label="My Document" DataType="System.String" IsReference="True" />
</Properties>
```

## <a name="see-also"></a>Voir aussi

- [Mapper les dépendances à travers vos solutions](../modeling/map-dependencies-across-your-solutions.md)
- [Utiliser des cartes de code pour déboguer vos applications](../modeling/use-code-maps-to-debug-your-applications.md)
- [Rechercher des problèmes potentiels à l’aide des analyseurs de carte du code](../modeling/find-potential-problems-using-code-map-analyzers.md)