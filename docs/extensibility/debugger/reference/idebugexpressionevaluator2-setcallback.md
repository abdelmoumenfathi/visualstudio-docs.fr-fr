---
title: IDebugExpressionEvaluator2::SetCallback | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugExpressionEvaluator2::SetCallback
- SetCallback
ms.assetid: 31e3a99e-e784-44a3-8b19-cc5ef31ed546
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 046064aedf82a1f0babf50971a0d28fdcc826ada
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211734"
---
# <a name="idebugexpressionevaluator2setcallback"></a>IDebugExpressionEvaluator2::SetCallback
Permet l’évaluateur d’expression (EE) spécifier l’interface de rappel que le moteur du débogueur (dé) utilisera pour lire les paramètres de mesure.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetCallback (
    IDebugSettingsCallback2* pCallback
);
```

```csharp
int SetCallback (
    IDebugSettingsCallback2 pCallback
);
```

## <a name="parameters"></a>Paramètres
`pCallback`\
[in] Interface à utiliser pour le rappel de paramètres.

## <a name="return-value"></a>Valeur de retour
En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.

## <a name="remarks"></a>Notes
Cette méthode fournit une interface avec le Gestionnaire de débogage de session un évaluateur d’expression peut utiliser pour lire les paramètres de mesure. Il est utile dans le débogage distant pour lire les métriques sur le [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ordinateur.

## <a name="example"></a>Exemple
Les exemples suivants montrent comment implémenter cette méthode pour un **CEE** objet qui expose le [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md) interface.

```cpp
HRESULT CEE::SetCallback(IDebugSettingsCallback2* in_pCallback)
{
    // precondition
    INVARIANT( this );

    // function body
    if (NULL != this->m_LanguageSpecificUseCases.pfSetCallback)
    {
        EEDomain::fSetCallback DomainVal =
        {
            in_pCallback
        };

        BOOL bSuccess = (*this->m_LanguageSpecificUseCases.pfSetCallback)(DomainVal);
        ENSURE( bSuccess );
    }

    // postcondition
    INVARIANT( this );

    return S_OK;
}
```

## <a name="see-also"></a>Voir aussi
- [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)
