---
title: Concepteur d’activités throw | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: db909618971eeab2d92506d1c29b06290aa9263b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62976617"
---
# <a name="throw-activity-designer"></a>Concepteur d'activités Throw
Le **lever** ActivityDesigner est utilisé pour créer et configurer un <xref:System.Activities.Statements.Throw> activité.  
  
## <a name="the-throw-activity"></a>Activité Throw  
 L'activité <xref:System.Activities.Statements.Throw> lève une exception.  
  
### <a name="using-the-throw-activity-designer"></a>Utilisation du concepteur d'activités Throw  
 Le **lever** Concepteur d’activités peut être trouvé dans le **gestion des erreurs** catégorie de la **boîte à outils**, qui est accessible en cliquant sur le **boîte à outils**onglet sur le côté gauche de la [!INCLUDE[wfd2](../includes/wfd2-md.md)] (ou bien, sélectionnez **barre d’outils** à partir de la **vue** menu ou CTRL + ALT + X.)  
  
 Le **lever** Concepteur d’activités peut être déplacé de la **boîte à outils** et déposé dans le [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface, là où les activités sont généralement placées, par exemple dans un <xref:System.Activities.Statements.Sequence>. Cette opération crée un <xref:System.Activities.Statements.Throw> activité avec une valeur par défaut **DisplayName** throw. Le <xref:System.Activities.Activity.DisplayName%2A> valeur peut être modifiée dans l’en-tête de la **lever** Concepteur d’activités ou dans le **DisplayName** case de la grille des propriétés. La propriété <xref:System.Activities.Statements.Throw.Exception%2A> doit être modifiée dans la grille des propriétés.  
  
### <a name="the-throw-properties"></a>Propriétés de Throw  
 Le tableau suivant présente les propriétés de <xref:System.Activities.Statements.Throw> et décrit comment elles sont utilisées dans le concepteur.  
  
|Nom de la propriété|Obligatoire|Utilisation|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Spécifie le nom convivial facultatif de l'activité <xref:System.Activities.Statements.Throw>. La valeur par défaut est Throw.|  
|<xref:System.Activities.Statements.Throw.Exception%2A>|True|Exception à lever. Cette exception doit dériver de <xref:System.Exception>. Pour spécifier l'exception, tapez une expression Visual Basic dans la grille des propriétés.|  
  
## <a name="see-also"></a>Voir aussi  
 [Collection](../workflow-designer/collection-activity-designers.md)   
 [rethrow](../workflow-designer/rethrow-activity-designer.md)   
 [Concepteur d’activités throw](../workflow-designer/throw-activity-designer.md)   
 [TryCatch](../workflow-designer/trycatch-activity-designer.md)