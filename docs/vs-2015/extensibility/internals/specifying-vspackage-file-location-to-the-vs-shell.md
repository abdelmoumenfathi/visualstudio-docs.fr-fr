---
title: Spécifiant l’emplacement du fichier VSPackage au shell Visual Studio | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, file location
- VSPackages, managed package file location
ms.assetid: beb8607a-4183-4ed2-9ac8-7527f11513b1
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c0662bfe22b4c78bb754bbac2fbfdd281a4a7bce
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63408522"
---
# <a name="specifying-vspackage-file-location-to-the-vs-shell"></a>Spécification de l’emplacement du fichier VSPackage au shell Visual Studio
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] doit être en mesure de localiser l’assembly DLL à charger le VSPackage. Vous pouvez le localiser de différentes manières, comme décrit dans le tableau suivant.  
  
|Méthode|Description|  
|------------|-----------------|  
|Utilisez la clé de Registre de base de code.|La clé de la base de code peut être utilisée pour diriger [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] pour charger l’assembly VSPackage à partir de n’importe quel chemin d’accès de fichier complet. La valeur de la clé doit être le chemin d’accès de fichier à la DLL. C’est la meilleure façon d’avoir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] de charger l’assembly de votre package. Cette technique est parfois appelée « CodeBase/privée installation directory technique. » Lors de l’inscription la valeur de la base de code est passée pour les classes d’attributs d’inscription via une instance de la <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.RegistrationContext> type.|  
|Placer la DLL dans le **PrivateAssemblies** directory.|Placez l’assembly dans le **PrivateAssemblies** sous-répertoire de le [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] directory. Assemblys situés dans **PrivateAssemblies** sont détectées automatiquement, mais ne sont pas visibles dans le **ajouter des références** boîte de dialogue. La différence entre **PrivateAssemblies** et **PublicAssemblies** est que les assemblys dans **PublicAssemblies** sont énumérés dans le **ajouter des références**  boîte de dialogue. Si vous choisissez de ne pas utiliser la technique « répertoire d’installation de base de code/privée », vous devez installer dans le **PrivateAssemblies** directory.|  
|Utiliser un assembly avec nom fort et la clé de Registre d’Assembly.|La clé d’Assembly peut être utilisée pour indiquer explicitement [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] pour charger un nom fort nommé assembly VSPackage. La valeur de la clé doit être le nom fort de l’assembly.|  
|Placer la DLL dans le **PublicAssemblies** directory.|Enfin, l’assembly peut également être placé dans le **PublicAssemblies** sous-répertoire. Assemblys situés dans **PublicAssemblies** sont détectées automatiquement et apparaît également dans le **ajouter des références** boîte de dialogue dans [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].<br /><br /> Assemblys de VSPackage doivent uniquement être placés dans le **PublicAssemblies** directory s’ils contiennent les composants qui sont destinées à être réutilisé par d’autres développeurs VSPackage gérés. La majorité des assemblys ne répondent pas à ce critère.|  
  
> [!NOTE]
> Utiliser des assemblys avec nom fort, signés pour tous vos assemblys dépendants. Ces assemblys doivent également être installés dans votre propre répertoire ou le global assembly cache (GAC). Cela protège contre les conflits avec les assemblys qui portent le même nom de fichier de base, appelé liaison de nom de faible.
