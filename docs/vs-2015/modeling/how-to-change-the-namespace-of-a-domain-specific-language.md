---
title: 'Procédure : Modifier le Namespace d’un langage spécifique à un domaine | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, namespace
ms.assetid: f20c47e5-230d-4f0e-812f-5c6edb86866c
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e86fa8f220cdd31beae12e050a1cbaa592624a74
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65690560"
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Procédure : Modifier l’espace de nom d’un langage spécifique à un domaine
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vous pouvez modifier l’espace de noms d’un langage spécifique à un domaine. Vous devez apporter la modification dans le **Explorateur DSL**dans les propriétés du projet de Dsl Package et dans les informations de l’assembly.  
  
### <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Pour modifier l’espace de noms d’un langage spécifique à un domaine  
  
1. Dans **Explorateur DSL**, cliquez sur le **Dsl** nœud.  
  
2. Dans le **propriétés** fenêtre, de modifier le **Namespace** propriété.  
  
3. Enregistrez la solution et transformer les modèles.  
  
4. Sur le **projet** menu, cliquez sur **Dsl propriétés**.  
  
     Les propriétés de votre projet s’affichent.  
  
5. Cliquez sur l’onglet **Application** .  
  
6. Modifier le **par défaut d’espace de noms** propriété vers le nouveau nom de l’espace de noms.  
  
7. Si vous souhaitez également modifier le nom de l’assembly, modifiez le **propriété Assembly name.**  
  
8. Si vous avez modifié le nom d’Assembly, ouvrez DslPackage\Package.tt et mettre à jour cette ligne :  
  
     `string dslAssembly = "YourDSLassembly.Dsl.dll";`  
  
9. Si vous avez écrit n’importe quel code personnalisé, veillez à modifier les références d’espace de noms et classe dans les fichiers de code.  
  
10. Réinitialiser l’instance expérimentale de Visual Studio.  
  
    1. Supprimer **\Users\\**_{nom de votre}_**\AppData\Local\Microsoft\VisualStudio\\\*Exp**  
  
    2. Sur le Windows **Démarrer** menu, choisissez **tous les programmes**, **Microsoft Visual Studio 2010 SDK**, **outils**, **réinitialiser le Instance expérimentale**.  
  
11. Sur le **Build** menu, choisissez **régénérer la Solution**.  
  
## <a name="see-also"></a>Voir aussi  
 [Glossaire des Outils Domain-Specific Language](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
