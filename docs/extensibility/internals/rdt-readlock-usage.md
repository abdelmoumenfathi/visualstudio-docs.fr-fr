---
title: Utilisation de RDT_ReadLock | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- RDT_ReadLock
- visible
- RDT_EditLock
- invisible
ms.assetid: b935fc82-9d6b-4a8d-9b70-e9a5c5ad4a55
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 04997bfed66da015c4aef82f4741218c88b9ecd1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62859362"
---
# <a name="rdtreadlock-usage"></a>Utilisation de RDT_ReadLock

[_VSRDTFLAGS. RDT_ReadLock](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS.RDT_ReadLock>) est un indicateur qui fournit la logique pour le verrouillage d’un document dans la Table (documents en cours), qui est la liste de tous les documents actuellement ouverts dans l’IDE Visual Studio. Cet indicateur détermine quand les documents sont ouverts, et si le document est visible dans l’interface utilisateur ou stockées de manière invisible en mémoire.

En général, vous utilisez [_VSRDTFLAGS. RDT_ReadLock](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS.RDT_ReadLock>) lorsque une des opérations suivantes est remplie :

- Vous souhaitez ouvrir un document de façon invisible et en lecture seule, mais il n’est pas encore établie qui <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> doit êtes bien le propriétaire.

- Vous souhaitez que l’utilisateur pour être invité à enregistrer un document qui a été ouvert de manière invisible avant que l’utilisateur, il s’affiche dans l’interface utilisateur et a tenté de fermer.

## <a name="how-to-manage-visible-and-invisible-documents"></a>Comment gérer des Documents Visible et Invisible

Lorsqu’un utilisateur ouvre un document dans l’interface utilisateur, un <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> propriétaire pour le document doit être établie et un [_VSRDTFLAGS. RDT_EditLock](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS.RDT_EditLock>) l’indicateur doit être défini. Si aucun <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> propriétaire peut être établi, puis le document n’est pas enregistré lorsque l’utilisateur clique sur **Enregistrer tout** ou ferme l’IDE. Cela signifie que si un document est ouvert de manière invisible où il est modifié dans la mémoire, et l’utilisateur est invité à enregistrer le document lors de l’arrêt ou enregistré si **Enregistrer tout** est choisie, puis un `RDT_ReadLock` ne peut pas être utilisé. Au lieu de cela, vous devez utiliser un `RDT_EditLock` et inscrire un <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> lorsqu’un [__VSREGDOCLOCKHOLDER. RDLH_WeakLockHolder](<xref:Microsoft.VisualStudio.Shell.Interop.__VSREGDOCLOCKHOLDER.RDLH_WeakLockHolder>) indicateur.

## <a name="rdteditlock-and-document-modification"></a>RDT_EditLock et Modification de documents

L’indicateur précédent mentionné indique que l’ouverture invisible du document génèrera son `RDT_EditLock` lorsque le document est ouvert par l’utilisateur dans un texte visible **DocumentWindow**. Lorsque cela se produit, l’utilisateur est présenté avec un **enregistrer** invite lorsque le texte visible **DocumentWindow** est fermé. `Microsoft.VisualStudio.Package.Automation.OAProject.CodeModel` les implémentations qui utilisent le <xref:Microsoft.VisualStudio.Shell.Interop.IVsInvisibleEditorManager> service fonctionnent initialement lorsque seul un `RDT_ReadLock` est effectuée (par exemple, lorsque le document est ouvert de façon invisible pour analyser les informations). Ultérieurement, si le document doit être modifié, puis le verrou est mis à niveau vers un faible **RDT_EditLock**. Si l’utilisateur ouvre ensuite le document dans un texte visible **DocumentWindow**, le `CodeModel`de faible `RDT_EditLock` est libéré.

Si l’utilisateur ferme puis le **DocumentWindow** et choisit **non** lorsque vous êtes invité à enregistrer le document ouvert, puis le `CodeModel` implémentation supprime toutes les informations dans le document et rouvre le document à partir du disque de manière invisible la prochaine fois que plus d’informations est nécessaire pour le document. La subtilité de ce comportement est une instance où l’utilisateur ouvre le **DocumentWindow** du document ouvert invisible, modifie, il ferme et choisit ensuite **non** lorsque vous êtes invité à enregistrer le document. Dans ce cas, si le document a un `RDT_ReadLock`, le document ne sera pas réellement fermé, puis le document modifié restera ouvert de manière invisible en mémoire, même si l’utilisateur choisi de ne pas enregistrer le document.

Si l’ouverture invisible du document utilise un faible `RDT_EditLock`, puis il donne son verrou lorsque l’utilisateur ouvre le document visiblement et aucun autre verrou n’est maintenu. Lorsque l’utilisateur ferme le **DocumentWindow** et choisit **non** lorsque vous êtes invité à enregistrer le document, le document doit être fermé à partir de la mémoire. Cela signifie que le client invisible doit écouter les événements RDT effectuer le suivi de cet événement. La prochaine fois que le document est requis, le document doit être rouverte.