---
title: Structure VSPackage (VSPackage de contrôle de code Source) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, structure
- source control packages, VSPackage overview
ms.assetid: 92722be7-b397-48c3-a7a7-0b931a341961
caps.latest.revision: 27
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 08bb0a296daca0de1c02b905a75fb10ce05f254e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58950589"
---
# <a name="vspackage-structure-source-control-vspackage"></a>Structure VSPackage (VSPackage de contrôle de code source)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Le Kit de développement du Package du contrôle de Source fournit des directives pour la création d’un VSPackage qui autorisent un implémenteur de contrôle de source à intégrer ses propres fonctionnalités de contrôle de code source avec le [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] environnement. Un VSPackage est un composant COM qui est généralement chargé à la demande par le [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] l’environnement de développement intégré (IDE) en fonction des services qui sont publiés par le package dans ses entrées de Registre. Chaque VSPackage doit implémenter le <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>. Un VSPackage consomme généralement les services proposés par le [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE et offre des services de son propre.  
  
 Un VSPackage déclare ses éléments de menu et établit un état d’élément par défaut via le fichier .vsct. Le [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE affiche les éléments de menu dans cet état jusqu'à ce que le VSPackage est chargé. Par la suite, le l’implémentation VSPackage de la <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> méthode est appelée pour activer ou désactiver des éléments de menu.  
  
## <a name="source-control-package-characteristics"></a>Caractéristiques de Package de contrôle de code source  
 Un contrôle de code source VSPackage est profondément intégré à [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 La sémantique de VSPackage est les suivantes :  
  
- Interface à implémenter car elle est un VSPackage (le `IVsPackage` interface)  
  
- Implémentation de la commande de l’interface utilisateur (fichier .vsct et l’implémentation de la <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interface)  
  
- L’inscription du VSPackage avec [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
  Le VSPackage de contrôle de code source doit communiquer avec ces autres [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] entités :  
  
- Projets  
  
- Éditeurs  
  
- Solutions  
  
- Windows  
  
- La table de document en cours d’exécution  
  
### <a name="visual-studio-environment-services-that-may-be-consumed"></a>Services de l’environnement Visual Studio qui peuvent être consommés  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 Service de SVsRegisterScciProvider  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>  
  
### <a name="vsip-interfaces-implemented-and-called"></a>VSIP Interfaces implémentées et appelées  
 Un package de contrôle de code source est un VSPackage, et par conséquent, il peut interagir directement avec les autres packages VS qui sont inscrits avec [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Afin de fournir la gamme complète des fonctionnalités de contrôle de code source, un contrôle de code source VSPackage peut traiter des interfaces fournies par les projets ou l’interpréteur de commandes.  
  
 Chaque projet dans [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] doit implémenter le <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3> à être reconnue comme un projet au sein du [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE. Toutefois, cette interface n’est pas spécialisée suffisant pour le contrôle de code source. Les projets qui sont censées être sous la source de contrôle implémentent la <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>. Cette interface est utilisée par le VSPackage de contrôle de code source pour interroger un projet pour son contenu et lui fournir des glyphes et informations de liaison (les informations nécessaires pour établir une connexion entre l’emplacement du serveur et l’emplacement du disque d’un projet qui est sous contrôle de code source).  
  
 Le contrôle de code source VSPackage implémente le <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>, ce qui permet à son tour des projets pour s’inscrire pour le contrôle de code source et de récupérer des glyphes de leur état.  
  
 Pour obtenir une liste complète des interfaces dont un VSPackage de contrôle de code source doit tenir compte, consultez [des Services et des Interfaces](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Éléments de conception](../../extensibility/internals/source-control-vspackage-design-elements.md)   
 [Interfaces et services associés](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)
