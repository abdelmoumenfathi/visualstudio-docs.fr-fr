---
title: Exemple de complément Excel pour le test codé de l’interface utilisateur | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests, Excel Add-in sample
ms.assetid: 2cd52d1a-4c35-43ca-8a84-9c79dabd907f
caps.latest.revision: 18
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8588efe9ce460a34fc71f44bc0116b5977afe7aa
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65705939"
---
# <a name="sample-excel-add-in-for-coded-ui-testing"></a>Exemple de complément Excel pour le test codé de l'interface utilisateur
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cet exemple de complément pour [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] est particulièrement conçu pour prendre en charge des tests codés de l'interface utilisateur de feuilles de calcul Excel qui sont enregistrés et exécutés dans Visual Studio Enterprise. Le complément est créé à l’aide de Visual Studio Tools pour Office.  
  
 Pour plus d’informations sur la création d’un complément à Excel, consultez [procédure pas à pas : Création de votre premier complément pour Excel](https://msdn.microsoft.com/library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f) ou effectuez une recherche MSDN pour « complément Excel ».  
  
 Bien que le complément Excel ne soit pas le sujet principal de cette documentation sur l’extension du test codé de l’interface utilisateur pour Excel, voici quelques commentaires utiles.  
  
 Parties importantes de ce complément :  
  
- Classe `ThisAddIn` : gère le canal .NET Remoting entre le `ExcelUICommunicator` et l’[exemple d’extension du test codé de l’interface utilisateur pour Excel](../test/sample-coded-ui-test-extension-for-excel.md).  
  
- `ExcelCodedUIAddinHelper_TemporaryKey.pfx` : certificat de sécurité pour tester le complément.  
  
- Classe `ExcelUICommunicator` : cette classe implémente l’interface `IExcelUICommunication`.  
  
## <a name="thisaddin-class"></a>Classe ThisAddIn  
 La plupart de cette classe est en fait généré par Visual Studio Tools pour Office dans le fichier `ThisAddIn.Designer.cs` quand vous créez votre projet de complément Excel.  
  
 Les membres que vous devez implémenter sont les gestionnaires d'événements : `ThisAddIn_Startup()` et `ThisAddIn_Shutdown()`. Leur but est d'initialiser ou de fermer le canal .NET Remoting utilisé par le `ExcelUICommunicator`.  
  
## <a name="excelcodeduiaddinhelpertemporarykeypfx"></a>ExcelCodedUIAddinHelper_TemporaryKey.pfx  
 Ce fichier contient un certificat de sécurité temporaire qui est généré par Visual Studio Tools pour Office et autorise l’assembly du complément à fonctionner dans le processus Excel pour tester le complément et l’extension. Vous devez supprimer ce certificat et soit en créer un nouveau sous l’onglet **Signature** de la fenêtre **Propriétés** du projet, soit attacher votre propre certificat de test.  
  
## <a name="exceluicommunicator-class"></a>Classe ExcelUICommunicator  
 Cette classe implémente l'interface `IExcelUITestCommunication` et obtient les informations de l'interface utilisateur demandée à partir du modèle objet Excel. Pour plus d’informations, consultez [Exemple d’interface Communicator Excel](../test/sample-excel-communicator-interface.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Extension des tests codés de l’interface utilisateur et des enregistrements des actions pour prendre en charge Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)   
 [Procédure pas à pas : Création de votre complément VSTO pour Excel](https://msdn.microsoft.com/library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)   
 [Développement Office et SharePoint](https://msdn.microsoft.com/library/2ddec047-263a-4901-a54c-a15fc8472329)
