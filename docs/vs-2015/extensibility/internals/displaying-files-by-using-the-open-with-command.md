---
title: Afficher les fichiers à l’aide de l’ouvrir avec la commande | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project types, supporting Open With command
- Open With command
- persistence, supporting Open With command
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: de43b6c4f441f8c6bde2d6c248274aed3937a7ee
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63408809"
---
# <a name="displaying-files-by-using-the-open-with-command"></a>Affichage de fichiers à l’aide de la commande Ouvrir avec
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Un projet peut demander à l’IDE pour afficher le **ouvrir avec** boîte de dialogue. Cette demande invite l’utilisateur à ouvrir un fichier qui comporte une sélection d’éditeurs standard. Les étapes suivantes décrivent ce processus.  
  
1. Les appels de projet <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, en spécifiant la valeur de OSE_UseOpenWithDialog pour la `OSEOpenDocEditor` paramètre.  
  
2. Selon l’extension de nom de fichier du document, l’IDE détermine les éditeurs répertoriés dans le peut Registre ouvrir le document spécifié et affiche ces informations dans le **ouvrir avec** boîte de dialogue.  
  
    > [!NOTE]
    > Les projets qui ont un éditeur intrinsèque qui doit être inclus dans le **ouvrir avec** boîte de dialogue doit inscrire une fabrique d’éditeur pour chaque éditeur de ce type. Éditeurs intrinsèques fonctionnent uniquement avec un type particulier de projet, qui est appliquée dans l’implémentation de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> (méthode). L’IDE a une fabrique d’éditeur intégré pour l’éditeur de texte principal et l’éditeur binaire. L’IDE crée également une instance d’une fabrique d’éditeur pour le compte de chaque association de fichiers Windows inscrite. Un exemple de ce type de fichier est Microsoft Word.  
  
3. Dès que l’utilisateur sélectionne un élément à partir de la **ouvrir avec** boîte de dialogue, puis l’IDE ouvre le document en appelant <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> (méthode). Pour plus d'informations, voir [Procédure : Ouvrir des éditeurs Standard](../../extensibility/how-to-open-standard-editors.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Ouvrir et enregistrer des éléments de projet](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Afficher les fichiers à l’aide de la commande Ouvrir un fichier](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)   
 [Guide pratique pour ouvrir des éditeurs standard](../../extensibility/how-to-open-standard-editors.md)
