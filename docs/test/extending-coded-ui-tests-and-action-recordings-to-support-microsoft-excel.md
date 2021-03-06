---
title: Étendre des tests codés de l’interface utilisateur et des enregistrements des actions
ms.date: 11/04/2016
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 07cdc27cb47a6de46585f573d78b5af00631c2a2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63002396"
---
# <a name="extend-coded-ui-tests-and-action-recordings"></a>Étendre des tests codés de l’interface utilisateur et des enregistrements des actions

L'infrastructure de test pour les tests codés de l'interface utilisateur et les enregistrements des actions ne prend pas en charge toutes les interfaces utilisateur possibles. Elle risque de ne pas prendre en charge l’interface utilisateur spécifique que vous souhaitez tester. Par exemple, vous ne pouvez pas créer immédiatement un test codé de l’interface utilisateur ou un enregistrement des actions pour une feuille de calcul Microsoft Excel. Toutefois, vous pouvez créer votre propre extension de l'infrastructure de test codé de l'interface utilisateur, qui prend en charge votre interface utilisateur spécifique en tirant parti de l’extensibilité du framework de test codé de l'interface utilisateur.

![Architecture du test IU](../test/media/ui_testarch.png)

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

## <a name="sample-extension-to-test-microsoft-excel"></a>Exemple d’extension pour tester Microsoft Excel

Ce [billet de blog](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/3-introducing-sample-excel-extension/) contient un lien vers un [exemple d’extension](https://msdnshared.blob.core.windows.net/media/MSDNBlogsFS/prod.evol.blogs.msdn.com/CommunityServer.Components.PostAttachments/00/09/94/38/24/ExcelPluginSample.zip) de framework de test codé de l’interface utilisateur. Vous pouvez également voir l’intégralité de la [série de billets de blog sur l’extensibilité du test codé de l'interface utilisateur](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/series-on-coded-ui-test-extensibility/).

> [!NOTE]
> L'exemple est conçu pour être utilisé avec Microsoft Excel 2010. Il peut fonctionner ou pas avec d’autres versions d’Excel.

## <a name="see-also"></a>Voir aussi

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [Utiliser l’automatisation de l’interface utilisateur pour tester votre code](../test/use-ui-automation-to-test-your-code.md)
- [Bonnes pratiques pour les tests codés de l’interface utilisateur](../test/best-practices-for-coded-ui-tests.md)
- [Plateformes et configurations prises en charge pour les tests codés de l’interface utilisateur et les enregistrements des actions](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)