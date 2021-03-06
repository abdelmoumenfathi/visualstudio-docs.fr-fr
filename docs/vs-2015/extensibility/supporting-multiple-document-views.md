---
title: Prise en charge plusieurs vues de Document | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - multiple document views
ms.assetid: c7ec2366-91c4-477f-908d-e89068bdb3e3
caps.latest.revision: 26
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9377fc12db8cedba65a418fd32b82a1421bd9b43
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58951966"
---
# <a name="supporting-multiple-document-views"></a>Prise en charge de vues de document multiples
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez fournir plusieurs vues d’un document en créant des données de document distinct et les objets de vue de document pour votre éditeur. Certains cas dans lesquels une vue de document supplémentaire serait utile sont :  
  
- Nouvelle prise en charge de fenêtre : Vous souhaitez que votre éditeur pour fournir deux ou plusieurs vues du même type, afin qu’un utilisateur qui possède déjà une fenêtre Ouvrir dans l’éditeur peut ouvrir une nouvelle fenêtre en sélectionnant le **nouvelle fenêtre** commande à partir de la **fenêtre** menu.  
  
- Prise en charge les view du formulaire et de code : Vous souhaitez votre éditeur pour proposer des vues de types différents. [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], par exemple, fournit une vue de formulaire et un mode code.  
  
  Pour plus d’informations, consultez la procédure CreateEditorInstance dans le fichier EditorFactory.cs dans le projet de l’éditeur personnalisé créé par le modèle de Package Visual Studio. Pour plus d’informations sur ce projet, consultez [procédure pas à pas : Création d’un éditeur personnalisé](../extensibility/walkthrough-creating-a-custom-editor.md).  
  
## <a name="synchronizing-views"></a>Synchronisation des vues  
 Lorsque vous implémentez plusieurs vues, l’objet de données est responsable de toutes les vues sont synchronisées avec les données. Vous pouvez utiliser la gestion des interfaces sur les événements <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> pour synchroniser plusieurs vues avec les données.  
  
 Si vous n’utilisez pas le <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objet pour synchroniser plusieurs vues, vous devez implémenter votre propre système d’événement pour gérer les modifications apportées à l’objet de données de document. Vous pouvez utiliser différents niveaux de granularité pour plusieurs vues de mise à jour. Avec un paramètre de granularité maximale, en cours de frappe dans une vue d’autres vues sont mis à jour immédiatement. Avec une granularité minimale, les autres vues ne sont pas mises à jour jusqu'à ce qu’ils sont activés.  
  
## <a name="determining-whether-document-data-is-already-open"></a>Déterminer si les données de Document est déjà ouvert  
 La table de document en cours d’exécution (RDT) dans l’environnement de développement intégré (IDE) vous aide à déterminer si les données d’un document sont déjà ouverts, comme indiqué dans le diagramme suivant.  
  
 ![Graphique de DocDataView](../extensibility/media/docdataview.gif "Docdataview")  
Vues multiples  
  
 Par défaut, chaque vue (objet de vue de document) est contenue dans le cadre de sa propre fenêtre (<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>). Comme déjà mentionné plus haut, toutefois, les données de document peuvent figurer dans plusieurs vues. Pour activer cette option, Visual Studio vérifie la RDT pour déterminer si le document en question est déjà ouvert dans un éditeur. Lorsque l’IDE appelle <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> pour créer l’éditeur, une valeur non NULL est retournée dans le `punkDocDataExisting` paramètre indique que le document est déjà ouvert dans un autre éditeur. Pour plus d’informations sur la façon la RDT, consultez [Table de Document en cours d’exécution](../extensibility/internals/running-document-table.md).  
  
 Dans votre <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> implémentation, examiner l’objet de données de document renvoyé dans `punkDocDataExisting` pour déterminer si les données du document sont appropriées pour votre éditeur. (Par exemple, uniquement les données HTML doivent être affichées par un éditeur HTML.) Si c’est approprié, puis votre fabrique d’éditeur doit fournir une deuxième vue pour les données. Si le `punkDocDataExisting` paramètre n’est pas `NULL`, il est possible soit que l’objet de données de document est ouvert dans un autre éditeur ou, plus probablement, que les données de document sont déjà ouverts dans une vue différente avec même l’éditeur. Si les données du document sont ouverts dans un autre éditeur de votre fabrique d’éditeur ne prend pas en charge, Visual Studio ne parvient pas à ouvrir votre fabrique d’éditeur. Pour plus d'informations, voir [Procédure : Joindre des vues de données de document](../extensibility/how-to-attach-views-to-document-data.md).
