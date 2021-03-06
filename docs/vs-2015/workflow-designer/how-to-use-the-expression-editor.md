---
title: 'Procédure : Utiliser l’éditeur d’expressions | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ExpressionTextBox.UI
ms.assetid: b5f961dd-6dda-41a9-9cae-0383d479ef3d
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cc876426c18184c966c277e8dafb5a373da332b7
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63408384"
---
# <a name="how-to-use-the-expression-editor"></a>Procédure : Utiliser l’éditeur d’expressions
L'éditeur d'expressions est un contrôle de [!INCLUDE[wfd1](../includes/wfd1-md.md)] utilisé dans de nombreuses activités de flux de travail pour entrer et évaluer des expressions. Il fournit une expérience d’édition IDE complète, comprenant, entre autres fonctionnalités, IntelliSense, la colorisation, ParamInfo et les tildes d’erreur. Le compilateur valide l'expression après sa saisie. Si l'expression n'est pas valide, une icône d'erreur s'affiche. L’éditeur peut également être ouvert comme un **Éditeur d’Expression** boîte de dialogue.  
  
 Les expressions sont des valeurs littérales ou du code [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] liés à des arguments ou des propriétés. Elles contiennent des éléments de valeur (par exemple, des variables, des constantes, des littéraux ou des propriétés) combinés avec des opérations afin de produire une nouvelle valeur. Les expressions sont écrites à l'aide de la syntaxe VB.NET même si l'application se trouve dans un programme utilisant C#. Cela signifie que les majuscules ne sont pas, la comparaison est effectuée à l’aide un seul égal (« = ») au lieu de (« == »), les opérateurs booléens sont les mots « et » et « ou » au lieu des symboles « & & » et «&#124;&#124;», et **rien**  est utilisé au lieu de **null**. Pour plus d’informations sur les expressions et opérateurs dans [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] et pour obtenir des exemples, consultez [opérateurs et Expressions en Visual Basic](http://go.microsoft.com/fwlink/?LinkId=186818).  
  
 Le **Éditeur d’Expression** se comporte comme suit :  
  
- Si le focus n'est pas sur l'éditeur d'expressions, celui-ci a l'apparence d'un contrôle TextBlock normal.  
  
- Lorsque le focus se trouve sur l'éditeur d'expressions, celui-ci adopte l'apparence et le comportement du contrôle de l'éditeur d'expressions. Lorsqu'il perd le focus, il reprend l'apparence d'un TextBlock classique.  
  
- Si vous placez le focus sur l'éditeur d'expressions dans un Workflow Designer réhébergé, il se comporte comme un contrôle TextBox. Lorsque le Workflow Designer réhébergé perd le focus, l'éditeur d'expressions reprend l'apparence d'un TextBlock normal.  
  
> [!NOTE]
> IntelliSense pour l'éditeur d'expressions est uniquement disponible dans [!INCLUDE[vs2010](../includes/vs2010-md.md)]. Qu'il soit exécuté dans [!INCLUDE[vs2010](../includes/vs2010-md.md)] ou réhébergé, le compilateur valide l'expression une fois qu'elle a été entrée et l'éditeur d'expressions affiche une icône d'erreur si l'expression n'est pas valide.  
  
### <a name="using-the-expression-editor"></a>Utilisation de l'éditeur d'expressions  
  
1. Dans [!INCLUDE[vs2010](../includes/vs2010-md.md)], ouvrez un projet de flux de travail nouveau ou existant.  
  
2. Par exemple, ajoutez l'activité <xref:System.Activities.Statements.Assign> à votre flux de travail.  
  
    > [!NOTE]
    > Plusieurs activités de flux de travail ont des éditeurs d'expressions. Des TextBlocks d’expression s’affichent également dans le concepteur de variables, le concepteur d’arguments et le concepteur d’arguments dynamique. L'activité <xref:System.Activities.Statements.Assign> est utilisée à titre d'exemple.  
  
3. Cliquez sur l'éditeur d'expressions à gauche dans le concepteur d'activités pour l'activité <xref:System.Activities.Statements.Assign>.  
  
     Les chaînes en filigrane grises  **\<à >** et  **\<entrer une Expression VB >** est des chaînes de texte de la valeur par défaut pour les éditeurs d’expressions dans le <xref:System.Activities.Statements.Assign> activité.  
  
4. Entrez votre expression. Si vous entrez une chaîne, n'oubliez pas de l'entourer de guillemets. Si vous choisissez de lier l’argument Expression à une variable, n’utilisez pas de guillemets.  
  
     Lorsque vous avez fini, sélectionnez une région ou une zone en dehors de l'éditeur d'expressions pour déplacer le focus vers une autre partie du concepteur. Le compilateur valide alors l'expression, comme décrit précédemment.  
  
     Un autre manière d'entrer/modifier une expression consiste à cliquer sur les points de suspension en regard du nom de propriété dans la grille des propriétés. Cette opération ouvre le **Éditeur d’Expression** en tant que boîte de dialogue.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>