---
title: JavaScript et TypeScript dans Visual Studio 2019
ms.date: 03/27/2019
ms.technology: vs-javascript
ms.topic: conceptual
dev_langs:
- JavaScript
- TypeScript
- DHTML
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: '>= vs-2019'
ms.openlocfilehash: 3000510c6bb6079629a3df05909417593569c932
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62553253"
---
# <a name="javascript-and-typescript-in-visual-studio-2019"></a>JavaScript et TypeScript dans Visual Studio 2019

## <a name="overview"></a>Vue d'ensemble

Visual Studio 2019 assure une prise en charge complète du développement JavaScript, à la fois directement et avec le [langage de programmation TypeScript](http://www.typescriptlang.org), qui a été développé pour offrir une expérience de développement JavaScript plus productive et plus agréable, en particulier pour des projets à grande échelle. Il est possible d’écrire du code JavaScript ou TypeScript dans Visual Studio pour de nombreux types d’applications et services.

## <a name="javascript-language-service"></a>Service de langage JavaScript

L’expérience JavaScript dans Visual Studio 2019 s’appuie sur le même moteur que la prise en charge de TypeScript, ce qui assure une meilleure prise en charge de fonctionnalités, une plus grande richesse et une intégration immédiatement prête à l’emploi.

La possibilité de revenir à l’ancien service de langage JavaScript n’est plus disponible. Les utilisateurs disposent maintenant du nouveau service de langage JavaScript intégré. Il s’appuie uniquement sur le service de langage TypeScript, qui repose sur l’analyse statique, ce qui nous permet de proposer de meilleurs outils : votre code JavaScript bénéficie ainsi de fonctionnalités IntelliSense plus riches, basées sur les définitions de type. Le nouveau service est léger et consomme moins de mémoire que l’ancien, ce qui assure de meilleurs résultats lorsque le code prend de l’ampleur. Nous avons également amélioré les performances du service de langage pour gérer les projets volumineux.

## <a name="typescript-support"></a>Prise en charge de TypeScript

Visual Studio 2019 propose plusieurs options d’intégration de la compilation TypeScript dans un projet :

* [Le package NuGet TypeScript](https://www.nuget.org/packages/Microsoft.TypeScript.MSBuild) : lorsque le package NuGet pour TypeScript 3.2 (ou version ultérieure) est installé dans un projet, la version correspondante du service de langage TypeScript est chargée dans l’éditeur.
* Le kit de développement logiciel (SDK) TypeScript, disponible par défaut dans Visual Studio Installer, ainsi qu’un kit SDK en téléchargement autonome sur [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=TypeScriptTeam.typescript-331-vs2017).
* [Le package npm TypeScript](https://www.npmjs.com/package/typescript) : lorsque le package npm pour TypeScript 2.1 (ou version ultérieure) est installé dans un projet, la version correspondante du service de langage TypeScript est chargée dans l’éditeur.

Pour les projets développés dans Visual Studio 2019, nous vous encourageons à utiliser les packages npm et NuGet TypeScript afin de bénéficier d’une meilleure portabilité entre les plateformes et les environnements.

## <a name="projects"></a>Projets

Les applications JavaScript UWP ne sont plus prises en charge dans Visual Studio 2019. Il n’est pas possible de créer ni d’ouvrir de projets UWP JavaScript (fichiers portant l’extension *.jsproj*). Pour plus d’informations, voir notre documentation sur la [création d’applications web progressives (PWA)](https://docs.microsoft.com/microsoft-edge/progressive-web-apps/get-started) qui s’exécutent correctement sur Windows.
