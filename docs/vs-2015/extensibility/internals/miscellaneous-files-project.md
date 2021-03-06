---
title: Projet fichiers divers | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- files, adding existing files to solutions
- Miscellaneous Files project
- Solution Items folder
- files, opening with Miscellaneous Files project
ms.assetid: 93a278a8-d4f4-400b-8945-4f1b0a2b5bac
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9c128475ad9f5cb71b98325bbece4e524507a08b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58950262"
---
# <a name="miscellaneous-files-project"></a>Projet Fichiers divers
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Lorsqu’un utilisateur ouvre les éléments de projet, l’IDE assigne au projet fichiers divers tous les éléments qui ne sont pas membres de tous les projets dans une solution.  
  
 Projets jouent un rôle significatif dans la détermination d’éditeur qui est utilisé lorsqu’un utilisateur ouvre un élément de projet. Un projet peut être conçu pour ouvrir certains fichiers à l’aide d’un éditeur spécifique au projet ou un éditeur standard.  
  
 Un éditeur spécifique au projet nécessite généralement que l’utilisateur ont des connaissances spéciales ou utiliser des interfaces spéciales à partir du projet. Pour plus d'informations, voir [Procédure : Ouvrir des éditeurs spécifiques du projet](../../extensibility/how-to-open-project-specific-editors.md).  
  
 Un éditeur standard peut ouvrir n’importe quel fichier d’une extension spécifique dans n’importe quel projet. L’utilisateur peut personnaliser certains éditeurs standards, tels que le [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] éditeur de texte, pour les projets conserver, tout en conservant leur caractère public. Éditeurs standard sont créés à l’aide de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> (méthode).  
  
 Si aucun projet dans la solution ne répond qu’il peut ouvrir un élément de projet, l’IDE fournit un projet spécial appelé projet fichiers divers qui s’ouvre n’importe quel fichier.  
  
 Ce projet spécial fournit pour l’ouverture d’un fichier en dehors du contexte d’un projet. Lors du traitement de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A> (méthode), le projet fichiers divers répond toujours avec une priorité très basse. Par conséquent, les fichiers divers de projet toujours donne à n’importe quel projet de priorité plus élevée qui peut ouvrir les fichiers.  
  
 Le projet fichiers divers ne nécessite pas l’utilisateur de créer explicitement avec le **nouveau projet** boîte de dialogue. En outre, le projet fichiers divers ne gère pas définitivement une liste des membres du projet. Il utilise une fonctionnalité facultative pour enregistrer une liste des derniers fichiers utilisés pour chaque utilisateur.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument>   
 <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY>   
 [Guide pratique pour Ouvrez éditeurs spécifiques du projet](../../extensibility/how-to-open-project-specific-editors.md)   
 [Guide pratique pour Ouvrir des éditeurs Standard](../../extensibility/how-to-open-standard-editors.md)   
 [Ajout de projet et modèles d’élément de projet](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [Ajout d’un projet et de modèles d’élément de projet](../../extensibility/internals/adding-project-and-project-item-templates.md)
