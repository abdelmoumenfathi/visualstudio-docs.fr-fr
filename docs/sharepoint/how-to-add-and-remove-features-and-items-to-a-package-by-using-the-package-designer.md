---
title: 'Procédure : Ajouter et supprimer des fonctionnalités et des éléments dans un Package à l’aide du Concepteur de packages | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.PackageDesignerDesign
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 654773f5a5e46960f8c015cc6f731e16332fcdd7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62966976"
---
# <a name="how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer"></a>Procédure : Ajouter et supprimer des fonctionnalités et des éléments dans un package à l’aide du Concepteur de packages
  Lorsque vous créez une solution SharePoint, Visual Studio ajoute les fonctionnalités de SharePoint par défaut pour le package dans la solution. Avant son déploiement final, vous pouvez ajouter et supprimer des éléments de projet SharePoint et des fonctionnalités pour modifier le package SharePoint.

 Vous pouvez également utiliser l’Explorateur de package pour ajouter et supprimer des éléments de projet SharePoint. Vous pouvez également afficher et modifier la hiérarchie des éléments de projet SharePoint et des fonctionnalités qui sont placées dans le package (.wsp). Pour plus d'informations, voir [Procédure : Ajouter et supprimer des fonctionnalités et des éléments dans un Package à l’aide de l’Explorateur de package](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md).

## <a name="add-features-to-a-sharepoint-package"></a>Ajouter des fonctionnalités à un package SharePoint
 Vous pouvez utiliser le Concepteur de packages pour ajouter des fonctionnalités à un package SharePoint.

#### <a name="to-add-sharepoint-features-with-the-package-designer"></a>Pour ajouter des fonctionnalités de SharePoint avec le Concepteur de packages

1. Ouvrez le **Package Designer**.

    Pour plus d'informations, voir [Procédure : Personnaliser un package de solution SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).

2. Ajoutez une ou plusieurs fonctionnalités de SharePoint en effectuant une ou plusieurs des étapes suivantes :

   1. Double-cliquez sur chaque élément dans le **éléments dans la Solution** liste que vous souhaitez ajouter.

   2. Choisissez un élément que vous souhaitez ajouter, puis choisissez le **ajouter** bouton (>).

   3. Choisissez le **ajouter tout** bouton (>>) pour ajouter tous les éléments à la fois.

      Par exemple, vous pouvez double-cliquer sur un élément dans le **éléments dans la Solution** liste pour l’ajouter à la **éléments dans le Package** liste.

      Les éléments de projet SharePoint et les fonctionnalités apparaissent dans le **éléments dans le Package** liste.

## <a name="remove-features-from-a-sharepoint-package"></a>Supprimer des fonctionnalités d’un Package SharePoint
 Vous pouvez utiliser le Concepteur de packages pour supprimer des fonctionnalités à un package SharePoint.

#### <a name="to-remove-sharepoint-features-with-the-package-designer"></a>Pour supprimer des fonctionnalités SharePoint avec le Concepteur de packages

1. Dans le **éléments dans le Package** , sélectionnez un élément que vous souhaitez supprimer, puis choisissez le **supprimer** (<) bouton, ou choisissez le **supprimer tout** bouton (<<) à supprimer tous les éléments.

     Les éléments SharePoint s’affichent dans le **éléments dans la Solution** liste.

## <a name="see-also"></a>Voir aussi
- [Créer des packages de solution SharePoint](../sharepoint/creating-sharepoint-solution-packages.md)
- [Guide pratique pour Personnaliser un package de solution SharePoint](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)
- [Guide pratique pour Créer un Package](https://msdn.microsoft.com/b24be45c-e91d-49bb-afb0-7b265404214b)
