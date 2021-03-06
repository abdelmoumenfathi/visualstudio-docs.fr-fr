---
title: DOCCONTEXT_COMPARE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DOCCONTEXT_COMPARE
helpviewer_keywords:
- DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e36e9c3c0870cb81dd02f646636eeb758f1ddb62
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686247"
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
Spécifie les critères pour la comparaison de deux contextes de document.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_DOCCONTEXT_COMPARE {
    DOCCONTEXT_EQUAL         = 0x0001,
    DOCCONTEXT_LESS_THAN     = 0x0002,
    DOCCONTEXT_GREATER_THAN  = 0x0003,
    DOCCONTEXT_SAME_DOCUMENT = 0x0004
};
typedef DWORD DOCCONTEXT_COMPARE;
```

```csharp
enum enum_DOCCONTEXT_COMPARE {
    DOCCONTEXT_EQUAL         = 0x0001,
    DOCCONTEXT_LESS_THAN     = 0x0002,
    DOCCONTEXT_GREATER_THAN  = 0x0003,
    DOCCONTEXT_SAME_DOCUMENT = 0x0004
};
```

## <a name="members"></a>Membres
DOCCONTEXT_EQUAL recherche le premier contexte de document dans la liste qui est égale au contexte de document cible.

DOCCONTEXT_LESS_THAN recherche le premier contexte de document dans la liste qui est inférieur au contexte du document cible.

DOCCONTEXT_GREATER_THAN recherche le premier contexte de document dans la liste qui est supérieure dans le contexte du document cible.

DOCCONTEXT_SAME_DOCUMENT recherche le premier contexte de document dans la liste qui se trouve dans le même document que le contexte du document cible.

## <a name="remarks"></a>Notes
Passé en tant qu’argument à la [comparer](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md) (méthode).

Ces valeurs sont utilisées pour spécifier des critères de comparaison pour trouver le premier contexte de document dans une liste. Un contexte de document reçoit une liste des contextes de document à comparer lui-même contre via le `IDebugDocumentContext2::Compare` (méthode). Le premier contexte de document dans la liste pour laquelle l’opérateur de comparaison est `true` est alors retournée.

## <a name="requirements"></a>Spécifications
En-tête : msdbg.h

Espace de noms : Microsoft.VisualStudio.Debugger.Interop

Assembly : Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Voir aussi
- [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)
