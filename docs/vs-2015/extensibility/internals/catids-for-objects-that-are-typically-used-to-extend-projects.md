---
title: CATID des objets qui sont généralement utilisés pour étendre des projets | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, CATIDs
- GUIDs, VSPackages
- CATIDs for VSPackages
ms.assetid: 0c7fdb66-ed96-4b36-89f6-021bca573572
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1cf5bd504bb5f7090dc07bea32e73333c0f182d0
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58952101"
---
# <a name="catids-for-objects-that-are-typically-used-to-extend-projects"></a>CATID des objets qui sont généralement utilisés pour étendre des projets
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Le tableau suivant répertorie les CATID qui sont utilisés pour étendre `Project` et `ProjectItem` objets automation [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], [!INCLUDE[csprcs](../../includes/csprcs-md.md)], et [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] projets. Ces CATID est définis dans VSLangProj.olb.  
  
## <a name="listing-of-catids"></a>Liste des CATID  
  
|Nom|GUID|  
|----------|----------|  
|<xref:VSLangProj.PrjCATID.prjCATIDProject>|{610D4614-D0D5-11D2-8599-006097C68E81}|  
|<xref:VSLangProj.PrjCATID.prjCATIDProjectItem>|{610D4615-D0D5-11D2-8599-006097C68E81}|  
  
## <a name="visual-basic-catids"></a>CATID de Visual Basic  
 Le tableau suivant répertorie les CATID qui sont utilisés pour étendre [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] parcourir les objets. Elles sont toutes définies dans VSLangProj.olb.  
  
|Nom|GUID|  
|----------|----------|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDVBProjectBrowseObject>|{E0FDC879-C32A-4751-A3D3-0B3824BD575F}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDVBProjectConfigBrowseObject>|{67F8DD11-14EB-489b-87F0-F01C52AF3870}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDVBFileBrowseObject>|{EA5BD05D-3C72-40A5-95A0-28A2773311CA}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDVBFolderBrowseObject>|{932DC619-2EAA-4192-B7E6-3D15AD31DF49}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDVBReferenceBrowseObject>|{2289B812-8191-4e81-B7B3-174045AB0CB5}|  
  
## <a name="visual-c-catids"></a>CATID Visual c#  
 Le CATID suivantes peut être utilisées pour étendre [!INCLUDE[csprcs](../../includes/csprcs-md.md)] parcourir les objets. Elles sont toutes définies dans VSLangProj.olb.  
  
|Nom|GUID|  
|----------|----------|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDCSharpProjectBrowseObject>|{4EF9F003-DE95-4d60-96B0-212979F2A857}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDCSharpProjectConfigBrowseObject>|{A12CE10A-227F-4963-ADB6-3A43388513CA}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDCSharpFileBrowseObject>|{8D58E6AF-ED4E-48B0-8C7B-C74EF0735451}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDCSharpFolderBrowseObject>|{914FE278-054A-45DB-BF9E-5F22484CC84C}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDCSharpReferenceBrowseObject>|{2F0FA3B8-C855-4a4e-95A5-CB45C67D6C27}|  
  
## <a name="c-catids"></a>CATID de C++  
 Ce qui suit [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] CATID n’est pas exposées dans les bibliothèques de types dans système de projet [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .NET 2003 et doit être incluse dans votre code chaque fois que vous souhaitez étendre ces objets du projet. Ces CATID est incluses dans les bibliothèques de types dans les versions ultérieures de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
|Nom|GUID|  
|----------|----------|  
|`CVCProjectNode`|{EE8299CB-19B6-4f20-ABEA-E1FD9A33B683}|  
|`CVCFolderNode`|{EE8299CA-19B6-4f20-ABEA-E1FD9A33B683}|  
|`CVCFileNode`|{EE8299C9-19B6-4f20-ABEA-E1FD9A33B683}|  
  
 L’exemple de code suivant montre comment programmer ces CATID dans votre code.  
  
```  
const LPOLESTR CVCProjectNode::s_wszCATID = L"{EE8299CB-19B6-4f20-ABEA-E1FD9A33B683}";  
const LPOLESTR CVCFolderNode::s_wszCATID = L"{EE8299CA-19B6-4f20-ABEA-E1FD9A33B683}";  
const LPOLESTR CVCFileNode::s_wszCATID = L"{EE8299C9-19B6-4f20-ABEA-E1FD9A33B683}";  
```  
  
 Ce qui suit [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] CATID n’est pas également exposées dans les bibliothèques de types dans système de projet [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .NET 2003 et doit être incluse dans votre code chaque fois que vous souhaitez étendre ces objets du projet. Ces CATID est uniquement disponibles dans [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .NET 2003 et ne sera pas disponible dans les versions ultérieures de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
|Nom|GUID|  
|----------|----------|  
|`CVCAssemblyReferenceNode` **:**|{FE8299C9-19B6-4f20-ABEA-E1FD9A33B683}|  
|`CVCProjectReferenceNode`|{593DCFCE-20A7-48e4-ACA1-49ADE9049887}|  
|`CVCActiveXReferenceNode`|{9E8182D3-C60A-44f4-A74B-14C90EF9CACE}|  
|`CVCReferences`|{FE8299CA-19B6-4f20-ABEA-E1FD9A33B683}|  
  
 L’exemple de code suivant montre comment programmer ces CATID dans votre code :  
  
```  
const LPOLESTR CVCAssemblyReferenceNode::s_wszCATID = L"{FE8299C9-19B6-4f20-ABEA-E1FD9A33B683}";  
const LPOLESTR CVCProjectReferenceNode::s_wszCATID = L"{593DCFCE-20A7-48e4-ACA1-49ADE9049887}";  
const LPOLESTR CVCActiveXReferenceNode::s_wszCATID = L"{9E8182D3-C60A-44f4-A74B-14C90EF9CACE}";  
const LPOLESTR CVCReferences::s_wszCATID = L"{FE8299CA-19B6-4f20-ABEA-E1FD9A33B683}";  
```  
  
 Les GUID pour le [!INCLUDE[csprcs](../../includes/csprcs-md.md)] et [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] les types de projet sont affichés dans le tableau suivant.  
  
|Type de projet|GUID|  
|------------------|----------|  
|[!INCLUDE[csprcs](../../includes/csprcs-md.md)]|{FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}|  
|[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]|{F184B08F-C81C-45F6-A57F-5ABD9991F28F}|  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout de projet et modèles d’élément de projet](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [Inscription de modèles de projet et d’élément](../../extensibility/internals/registering-project-and-item-templates.md)
