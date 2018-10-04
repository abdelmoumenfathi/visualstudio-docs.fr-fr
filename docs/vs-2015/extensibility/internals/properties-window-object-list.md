---
title: Liste d’objets de fenêtre de propriétés | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Properties window, object list
ms.assetid: 6c159c9d-345d-4b23-8ddd-9839d338b62f
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 87592deaec57b5638336cf191f12896cccbcb5b3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47508338"
---
# <a name="properties-window-object-list"></a>Liste d’objets de la fenêtre Propriétés
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vous trouverez la dernière version de cette rubrique dans [liste d’objets de fenêtre de propriétés](https://docs.microsoft.com/visualstudio/extensibility/internals/properties-window-object-list).  
  
La liste d’objets dans le **propriétés** fenêtre est une liste déroulante qui vous permet de modifier la sélection à d’autres objets disponibles au sein d’une ou plusieurs fenêtres sélectionnés. Sélection d’un objet différent dans cette liste déclenche un appel à <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A> pour informer l’environnement qu’un nouvel objet a été sélectionné. Les informations affichées dans le **propriétés** fenêtre est ensuite modifiée pour afficher les propriétés associées à l’objet qui vient d’être sélectionné.  
  
## <a name="the-object-list"></a>La liste d’objets  
 La liste d’objets se compose de deux champs : le nom d’objet (affiché en gras) et le type d’objet.  
  
 Le nom de l’objet affiché à gauche du type d’objet en gras est récupéré à partir de l’objet lui-même à l’aide de la `Name` propriété fournie par le <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> interface. <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo.GetClassInfo%2A>, la seule méthode sur <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, retourne <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo> pour coclasse de cette interface. Le **propriétés** fenêtre utilise <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> pour obtenir le nom de la coclasse, qui s’affiche en tant que le nom d’objet dans la liste déroulante.  
  
 Si l’objet n’a pas un `Name` propriété, un nom n’est pas affichée dans la zone Nom de la liste d’objets. Si vous souhaitez que le nom affiché dans la liste d’objets, vous pouvez ajouter une propriété de nom à l’objet.  
  
 Si l’objet COM n’implémente pas <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, le **propriétés** fenêtre affiche le nom de l’interface à la place le nom de l’objet sur le côté gauche de la liste.  
  
## <a name="see-also"></a>Voir aussi  
 [Extension des propriétés](../../extensibility/internals/extending-properties.md)
