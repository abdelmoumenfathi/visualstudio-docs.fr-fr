---
title: Introduction à IntelliTest
ms.date: 05/02/2017
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Get started
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 92a5b5f6ffac7285dd1a22d7193ada74e3a90967
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62906845"
---
# <a name="get-started-with-microsoft-intellitest"></a>Bien démarrer avec Microsoft IntelliTest

* Si vous utilisez IntelliTest pour la première fois :
  * visionnez la [vidéo de Channel 9](https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Intellitest)
  * lisez cette [présentation sur MSDN Magazine](https://msdn.microsoft.com/magazine/dn904672.aspx)
  * lisez notre [documentation](../../test/generate-unit-tests-for-your-code-with-intellitest.md)
* Posez vos questions sur [Stack Overflow](http://stackoverflow.com/questions/tagged/intellitest)
* Lisez le reste de ce manuel de référence
* Imprimez cette page pour vous y référer rapidement

## <a name="important-attributes"></a>Attributs importants

* [PexClass](attribute-glossary.md#pexclass) marque un type contenant **PUT**
* [PexMethod](attribute-glossary.md#pexmethod) marque un **PUT**
* [PexAssumeNotNull](attribute-glossary.md#pexassumenotnull) marque un paramètre non Null

```csharp
using Microsoft.Pex.Framework;

[..., PexClass(typeof(Foo))]
public partial class FooTest {
    [PexMethod]
    public void Bar([PexAssumeNotNull]Foo target, int i) {
        target.Bar(i);
    }
}
```

* [PexAssemblyUnderTest](attribute-glossary.md#pexassemblyundertest) lie un projet de test à un projet
* [PexInstrumentAssembly](attribute-glossary.md#pexinstrumentassemblyattribute) spécifie un assembly à instrumenter

```csharp
[assembly: PexAssemblyUnderTest("MyAssembly")] // also instruments "MyAssembly"
[assembly: PexInstrumentAssembly("Lib")]
```

## <a name="helper-classes"></a> Classes d’assistance statiques importantes

* [PexAssume](static-helper-classes.md#pexassume) évalue les hypothèses (filtrage d’entrée)
* [PexAssert](static-helper-classes.md#pexassert) évalue les assertions
* [PexChoose](static-helper-classes.md#pexchoose) génère de nouveaux choix (entrées supplémentaires)
* [PexObserve](static-helper-classes.md#pexobserve) enregistre les valeurs dynamiques dans les tests générés

```csharp
[PexMethod]
void StaticHelpers(Foo target) {
    PexAssume.IsNotNull(target);

    int i = PexChoose.Value<int>("i");
    string result = target.Bar(i);

    PexObserve.ValueForViewing<string>("result", result);
    PexAssert.IsNotNull(result);
}
```

## <a name="got-feedback"></a>Vous avez des commentaires ?

Postez vos idées et demandes de fonctionnalités sur la [Communauté des développeurs](https://developercommunity.visualstudio.com/content/idea/post.html?space=8).
