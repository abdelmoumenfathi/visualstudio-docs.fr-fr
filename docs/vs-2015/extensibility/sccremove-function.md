---
title: Fonction SccRemove | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccRemove
helpviewer_keywords:
- SccRemove function
ms.assetid: 20830fdc-c0e9-4a5f-bf60-33f28874442f
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 62974f585fe164c7ccf7ea21a19d22939d806d73
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58953515"
---
# <a name="sccremove-function"></a>Fonction SccRemove
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Cette fonction supprime les fichiers du système de contrôle source.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccRemove(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 pvContext  
 [in] La structure de contexte de plug-in de contrôle de source.  
  
 hWnd  
 [in] Handle vers la fenêtre de l’IDE que le plug-in de contrôle de code source peut utiliser en tant que parent pour les boîtes de dialogue qu’il fournit.  
  
 nFiles  
 [in] Nombre de fichiers spécifiés dans le `lpFileNames` tableau.  
  
 lpFileNames  
 [in] Tableau des noms de chemin d’accès local complet des fichiers à supprimer.  
  
 lpComment  
 [in] Le commentaire à appliquer à chaque fichier en cours de suppression.  
  
 fOptions  
 [in] Indicateurs de commande (inutilisés).  
  
 pvOptions  
 [in] Options spécifiques au plug-in de contrôle source.  
  
## <a name="return-value"></a>Valeur de retour  
 L’implémentation de plug-in de contrôle de source de cette fonction est censée retourner l’une des valeurs suivantes :  
  
|Value|Description|  
|-----------|-----------------|  
|SCC_OK|La suppression a réussi.|  
|SCC_E_FILENOTCONTROLLED|Le fichier sélectionné n’est pas sous contrôle de code source.|  
|SCC_E_OPNOTSUPPORTED|Le système de contrôle de code source ne prend pas en charge cette opération.|  
|SCC_E_ISCHECKEDOUT|Impossible de supprimer un fichier, car un utilisateur n’est extrait.|  
|SCC_E_ACCESSFAILURE|Impossible d’accéder au système de contrôle source, probablement en raison de problèmes réseau ou de contention.|  
|SCC_E_NOTAUTHORIZED|L’utilisateur n’est pas autorisé à effectuer cette opération.|  
|SCC_E_NONSPECIFICERROR|Échec non spécifique ; fichier n’a pas été supprimé.|  
|SCC_I_OPERATIONCANCELED|L’opération a été annulée avant la fin.|  
  
## <a name="remarks"></a>Notes  
 Cette fonction supprime les fichiers du système de contrôle source, mais ne les supprime pas de disque dur local de l’utilisateur.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions d’API du plug-in de contrôle de code source](../extensibility/source-control-plug-in-api-functions.md)
