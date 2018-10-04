---
title: Vue d’ensemble du langage spécifique à un domaine outils Interface utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.editor
helpviewer_keywords:
- Domain-Specific Language Tools, user interface
ms.assetid: 81ae6b35-6819-41d0-953b-6b4ed81f9227
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 25d8f34488c0fee954eb9ab2d372750518433f4a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47493424"
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>Vue d'ensemble de l'interface utilisateur des outils de langage spécifique à un domaine
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [vue d’ensemble de l’Interface utilisateur des outils Domain-Specific Language](https://docs.microsoft.com/visualstudio/modeling/overview-of-the-domain-specific-language-tools-user-interface).  
  
Lorsque vous ouvrez pour la première fois une solution d’outils de langage spécifique à un domaine (outils DSL) dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], l’interface utilisateur doit ressembler à l’image suivante.  
  
 ![concepteur DSL](../modeling/media/dsl-designer.png "dsl_designer")  
  
 Le tableau suivant explique comment les parties de l’interface utilisateur sont utilisés.  
  
|**Élément**|**Définition**|  
|-----------------|--------------------|  
|Diagramme|Le diagramme affiche le modèle de domaine.<br /><br /> Le diagramme comporte deux parties. Côté « un » définit les types des éléments dans vos modèles. L’autre côté définit l’apparaissent de vos modèles sur l’écran.|  
|Boîte à outils|Faites glisser des outils à partir de la boîte à outils pour ajouter des classes de domaine et forme des types au diagramme. Pour ajouter des mappages de formes, des connecteurs et des relations, cliquez sur l’outil, puis cliquez sur le nœud source sur le diagramme, puis le nœud cible.|  
|explorateur DSL|**Explorateur DSL** s’affiche lorsqu’une définition DSL est la fenêtre active. Il montre la solution DSL sous forme d’arborescence. Explorateur DSL vous permet de modifier les fonctionnalités du modèle qui ne sont pas affichées sur le diagramme. Par exemple, vous pouvez ajouter des éléments de boîte à outils et basculez sur le processus de validation à l’aide de la **Explorateur DSL**.|  
|Fenêtre Détails DSL|Le **détails DSL** fenêtre affiche les propriétés du domaine des éléments du modèle qui vous permettent de contrôler la façon dont les éléments sont affichés, et comment les éléments sont copiés et supprimés.<br /><br /> -Par défaut, le **détails DSL** fenêtre s’affiche en regard du **liste d’erreurs** et **sortie** windows.|  
  
## <a name="the-domain-model-diagram"></a>Le diagramme de modèle de domaine  
 Le diagramme de modèle de domaine est divisé en deux parties. Un côté du diagramme montre les éléments et les relations dans le modèle. L’autre côté montre comment le modèle doit être affiché et inclut les formes qui sont utilisées pour afficher les éléments et les propriétés du diagramme de modèle. L’illustration suivante montre les éléments du diagramme.  
  
 ![concepteur DSL avec couloir](../modeling/media/dsl-desinger.png "dsl_desinger")  
  
 Le tableau suivant décrit certains des éléments du diagramme de modèle de domaine.  
  
|**Terme**|**Définition**|  
|--------------|--------------------|  
|Classe de domaine|Classes de domaine sont les types d’éléments dans vos modèles.<br /><br /> Une classe de domaine peut apparaître plusieurs fois dans un diagramme, s’il s’agit de la cible de plusieurs relations.<br /><br /> Pour ajouter une classe de domaine, faites glisser l’outil de classe de domaine à partir de la **boîte à outils** à la **Classes et relations** côté du diagramme.|  
|Relation de domaine|Relations de domaine sont les types de liens entre des éléments dans vos modèles.<br /><br /> Un *relation d’incorporation* indique que l’élément cible est détenu ou contenu par l’élément source et apparaît sous la forme d’une ligne pleine. Chaque élément dans un modèle doit être la cible d’une relation d’incorporation, afin que le modèle forme une arborescence. Un *relation de référence* indique un lien entre les éléments de modèle général et apparaît sous la forme d’une ligne en pointillés. N’importe quel élément peut avoir n’importe quel nombre de liens de référence.<br /><br /> Créer une relation en cliquant sur l’outil sur le **boîte à outils**, en cliquant sur la classe de domaine source, puis en cliquant sur la classe cible.|  
|Formes et connecteurs|Formes spécifient comment les éléments de modèle doivent être affichées sur un diagramme DSL., connecteurs spécifient des lignes dans un diagramme DSL qui peut être utilisé pour afficher les relations.<br /><br /> Pour créer une forme ou un connecteur, faites glisser l’outil pour la **éléments de diagramme** côté du diagramme.|  
|Mappages de formes|Une carte de forme s’affiche sous forme de ligne sur le diagramme de modèle de domaine, liaison d’une forme à la classe de domaine qui y sont affichées, ou un connecteur à la relation de domaine qu’il affiche.|  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble des outils Domain-Specific Language](../modeling/overview-of-domain-specific-language-tools.md)   
 [Glossaire des outils Domain-Specific Language](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)   
 [Personnalisation et extension d’un langage spécifique à un domaine](../modeling/customizing-and-extending-a-domain-specific-language.md)


