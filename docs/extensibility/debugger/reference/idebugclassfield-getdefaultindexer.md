---
title: IDebugClassField::GetDefaultIndexer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::GetDefaultIndexer
helpviewer_keywords:
- IDebugClassField::GetDefaultIndexer method
ms.assetid: 47ce4f45-3816-4b40-909c-5032d0692d75
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: eaaddbe6bb223e8e2987f8310f1d8e08d5602a01
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66206830"
---
# <a name="idebugclassfieldgetdefaultindexer"></a>IDebugClassField::GetDefaultIndexer
Obtient le nom de l’indexeur par défaut.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetDefaultIndexer( 
   BSTR* pbstrIndexer
);
```

```csharp
int GetDefaultIndexer(
   out string pbstrIndexer
);
```

## <a name="parameters"></a>Paramètres
`pbstrIndexer` [out] Retourne une chaîne contenant le nom de l’indexeur par défaut.

## <a name="return-value"></a>Valeur de retour
 En cas de réussite, retourne S_OK, ou retourne S_FALSE s’il n’existe aucun indexeur par défaut. Sinon, retourne un code d'erreur.

## <a name="remarks"></a>Notes
 L’indexeur par défaut d’une classe est la propriété qui est marquée comme étant le `Default` propriété pour l’accès aux tableaux. Ceci est spécifique à [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]. Voici un exemple d’un indexeur par défaut déclaré dans [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] et comment elle est utilisée.

```vb
Imports System.Collections;

Public Class Class1
    Private myList as Hashtable

    Default Public Property Item(ByVal Index As Integer) As Integer
        Get
            Return CType(List(Index), Integer)
        End Get
        Set(ByVal Value As Integer)
            List(Index) = Value
        End Set
    End Property
End Class

Function GetItem(Index as Integer) as Integer
    Dim classList as Class1 = new Class1
    Dim value as Integer

    ' Access array through default indexer
    value = classList(2)

    ' Access array through explicit property
    value = classList.Item(2)

    Return value
End Function
```

## <a name="see-also"></a>Voir aussi
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)