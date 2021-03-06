---
title: Visual Studio Command Table (. Fichiers VSCT) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, overview
- Visual Studio command table configuration files (VSCT), overview
ms.assetid: 1313adb4-add4-4e74-90e2-f4be522f5259
caps.latest.revision: 23
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cde3b86e19788c41df6e8f1c79a6bf829f491170
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65675243"
---
# <a name="visual-studio-command-table-vsct-files"></a>Fichiers Visual Studio Command Table (.Vsct)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Un fichier de configuration de table de commande est un fichier texte qui décrit l’ensemble des commandes qui contient un VSPackage. Le [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] commande les compilateur (VSTC) de table compile les fichiers de configuration XML (fichiers .vsct) en fichiers de sortie (.cto) de table de commande binaire. Les fichiers .cto résultants sont les mêmes que celles qui sont créées en utilisant le compilateur de table (CTC) de commande pour compiler des fichiers de configuration .ctc. Toutefois, les fichiers .vsct basé sur XML a certains avantages, notamment un éditeur XML et le XML IntelliSense.  
  
 Pour en savoir plus sur la syntaxe et la sémantique des fichiers .vsct, consultez [conception XML Command Table (. Fichiers VSCT)](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
  
## <a name="in-this-section"></a>Dans cette section  
 [Conception de fichiers XML Command Table (.Vsct)](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
 Explique comment concevoir des fichiers .vsct.  
  
 [Guide pratique pour créer un fichier .Vsct](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)  
 Compare les méthodes de création d’un fichier .vsct. Décrit le processus permettant de créer manuellement un nouveau fichier .vsct.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Schéma de référence XML VSCT](../../extensibility/vsct-xml-schema-reference.md)  
 Fournit des détails sur chaque section du fichier de configuration XML de table de commandes.  
  
 [Commande de Configuration de la Table (. Fichiers CTC)](https://msdn.microsoft.com/3413dda1-f372-4669-bcf0-c64d3463842c)  
 Présente une vue d’ensemble du format de fichier .ctc déconseillées.  
  
 [Comment VSPackages ajoute des éléments de l’interface utilisateur](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Décrit la spécification de format de table de commande.  
  
 [Ressources dans VSPackages](../../extensibility/internals/resources-in-vspackages.md)  
 Décrit comment utiliser les ressources non managées et non managées dans les VSPackages gérés.  
  
 [Commandes, menus et barres d’outils](../../extensibility/internals/commands-menus-and-toolbars.md)  
 Explique comment créer une interface utilisateur comprenant des menus, des barres d’outils et des listes déroulantes de commandes.
