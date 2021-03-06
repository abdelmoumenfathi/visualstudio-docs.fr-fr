---
title: À l’aide de la fenêtre tâches | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.paralleltasks
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, parallel tasks window
ms.assetid: bd5e0612-a0dc-41cf-a7af-1e87d0d5c35f
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 267a04e0d717bde311423aae7f35fba07ca6f39b
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65684036"
---
# <a name="using-the-tasks-window"></a>Utilisation de la fenêtre Tâches
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La fenêtre **Tâches** ressemble à la fenêtre **Threads**, hormis le fait qu'elle comporte des informations sur les objets <xref:System.Threading.Tasks.Task?displayProperty=fullName> , [task_handle](https://msdn.microsoft.com/library/b4af5b28-227d-4488-8194-0a0d039173b7) ou [WinJS.Promise](https://msdn.microsoft.com/library/windows/apps/br211867.aspx), et non pas sur chaque thread. Comme les threads, les tâches représentent des opérations asynchrones qui peuvent s'exécuter simultanément. Toutefois, plusieurs tâches peuvent s'exécuter sur le même thread. Consultez [programmation asynchrone dans JavaScript (applications du Windows Store)](https://msdn.microsoft.com/library/windows/apps/hh700330.aspx) pour plus d’informations.  
  
 Le code managé vous permet d’utiliser la fenêtre **Tâches** lorsque vous travaillez avec des objets <xref:System.Threading.Tasks.Task?displayProperty=fullName> ou avec les mots clés **await** et **async** (**Await** et **Asynchrone** en Visual Basic). Pour plus d’informations sur les tâches en code managé, consultez [à la programmation parallèle](https://msdn.microsoft.com/library/4d83c690-ad2d-489e-a2e0-b85b898a672d).  
  
 En code natif, vous pouvez utiliser la fenêtre **Tâches** lorsque vous travaillez avec des [groupes de tâches](https://msdn.microsoft.com/library/42f05ac3-2098-494a-ba84-737fcdcad077), des [algorithmes parallèles](https://msdn.microsoft.com/library/045dca7b-4d73-4558-a44c-383b88a28473), des [agents asynchrones](https://msdn.microsoft.com/library/6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a) et des [tâches légères](https://msdn.microsoft.com/library/9aba278c-e0c9-4ede-b7c6-fedf7a365d90). Pour plus d’informations sur les tâches en code natif, consultez [Runtime d’accès concurrentiel](https://msdn.microsoft.com/library/874bc58f-8dce-483e-a3a1-4dcc9e52ed2c).  
  
 En JavaScript, vous pouvez utiliser la fenêtre Tâches lorsque vous utilisez le code .then.  
  
 Vous pouvez utiliser la fenêtre **Tâches** chaque fois que l’exécution s’arrête dans le débogueur. Pour y accéder, dans le menu **Déboguer**, cliquez sur **Fenêtres**, puis sur **Tâches**. L’illustration suivante présente la fenêtre **Tâches** dans son mode par défaut.  
  
 ![Fenêtre Tâches parallèles](../debugger/media/parallel-tasks-window.png "Parallel_Tasks_Window")  
  
> [!NOTE]
> En code managé, <xref:System.Threading.Tasks.Task> qui a un état <xref:System.Threading.Tasks.TaskStatus>, <xref:System.Threading.Tasks.TaskStatus> ou <xref:System.Threading.Tasks.TaskStatus>, ne peut pas s'afficher dans la fenêtre Tâches lorsque les threads managés sont à l'état de veille ou à l'état de jonction.  
  
## <a name="tasks-column-information"></a>Informations sur les colonnes de la fenêtre Tâches  
 Les colonnes de la fenêtre **Tâches** contiennent les informations suivantes.  
  
|Nom de la colonne|Description|  
|-----------------|-----------------|  
|**Indicateurs**|Affiche les tâches avec indicateur et vous permet d’ajouter un indicateur à une tâche ou d’en supprimer un.|  
|**Icônes**|La flèche jaune indique la tâche actuelle. La tâche actuelle est la tâche supérieure du thread actuel.<br /><br /> Une flèche blanche indique la tâche d’arrêt, autrement dit, celle qui était actuelle lorsque le débogueur a été appelé.<br /><br /> L'icône de pause indique une tâche gelée par l'utilisateur. Vous pouvez geler et libérer une tâche en cliquant dessus avec le bouton droit dans la liste.|  
|**ID**|Numéro fourni par le système pour la tâche. En code natif, il s’agit de l’adresse de la tâche.|  
|**État**|État actuel (planifié, actif, bloqué, en attente ou terminé) de la tâche. Une tâche planifiée est une tâche qui n’a pas encore été exécutée et, par conséquent, qui de possède pas encore une pile d’appels, un thread assigné ou des informations connexes.<br /><br /> Une tâche active est une tâche qui était en train d'exécuter du code avant de s'arrêter dans le débogueur.<br /><br /> Une tâche en attente est une tâche bloquée qui attend le signal d'un événement, la libération d'un verrouillage ou la fin d'une autre tâche.<br /><br /> Une tâche bloquée est une tâche en attente dont le thread est bloqué par un autre thread.<br /><br /> Placez le curseur sur le **état** cellule d’une tâche bloquée ou en attente voir plus d’informations sur le bloc. **Avertissement :**  La fenêtre **Tâches** signale les interblocages uniquement pour les tâches bloquées utilisant une primitive de synchronisation prise en charge par le parcours du type d’attente (WCT). Par exemple, pour un interblocage <xref:System.Threading.Tasks.Task> objet, qui utilise le WCT, le débogueur signale **attente bloquée**. Pour une tâche bloquée gérée par le runtime d’accès concurrentiel qui n’utilise pas Wait Chain Traversal, le débogueur signale **En attente**. Pour plus d'informations sur WCT, consultez [Wait Chain Traversal](https://msdn.microsoft.com/library/ms681622\(VS.85\).aspx) (page éventuellement en anglais).|  
|**Heure de début**|Heure à laquelle la tâche est devenue active.|  
|**Durée**|Nombre de secondes durant lesquelles la tâche a été active.|  
|**Heure d'achèvement**|Heure à laquelle la tâche s’est terminée.|  
|**Emplacement**|Emplacement actuel dans la pile d’appels de la tâche. Pointez sur cette cellule pour visualiser l’ensemble de la pile des appels de la tâche. Les tâches planifiées ne disposent pas de valeur dans cette colonne.|  
|**Task**|Méthode initiale et tous les arguments passés à la tâche lorsqu'elle a été créée.|  
|**Parent**|ID de la tâche qui a créé cette tâche. Si rien n’est indiqué, la tâche n’a aucun parent. Ceci s'applique uniquement aux programmes gérés.|  
|**Assignation de thread**|ID et nom du thread sur lequel la tâche s'exécute.|  
|**État de retour**|État de la tâche lorsqu'elle est terminée. Les valeurs de retour d’état sont **réussite**, **Cancelled**, et **erreur**.|  
|**AppDomain**|Pour du code managé, domaine d’application dans lequel la tâche s’exécute.|  
|**task_group**|Pour du code natif, adresse de l’objet [task_group](https://msdn.microsoft.com/library/b4af5b28-227d-4488-8194-0a0d039173b7) qui a planifié la tâche. Pour les agents asynchrones et les tâches légères, cette colonne a la valeur 0.|  
|Process|ID du processus que la tâche exécute.|  
|État asynchrone|En matière de code managé, état de la tâche. Par défaut, cette colonne est masquée. Pour afficher cette colonne, ouvrez le menu contextuel pour l'une des en-têtes de colonnes. Sélectionnez **Colonnes**, **AsyncState**.|  
  
 Vous pouvez ajouter des colonnes à la vue en cliquant avec le bouton droit sur un en-tête de colonne et en sélectionnant ensuite les colonnes souhaitées. (Supprimez des colonnes en effaçant les sélections.) Vous pouvez également réorganiser les colonnes en les faisant glisser à gauche ou à droite. Le menu contextuel des colonnes est présenté dans l'illustration suivante.  
  
 ![Menu d’affichage contextuel dans la fenêtre Tâches parallèles](../debugger/media/parallel-tasks-contextmenu.png "Parallel_Tasks_ContextMenu")  
  
## <a name="sorting-tasks"></a>Tri de tâches  
 Pour trier des tâches en fonction des critères de colonne, cliquez sur l’en-tête d’une colonne. Par exemple, en cliquant sur le **ID** en-tête de colonne, vous pouvez trier les tâches par ID de tâche : 1,2,3,4,5 et ainsi de suite. Pour inverser l'ordre de tri, cliquez à nouveau sur l'en-tête de la colonne. La colonne et l'ordre de tri actuels sont indiqués par une flèche dans la colonne.  
  
## <a name="grouping-tasks"></a>Regroupement de tâches  
 Vous pouvez regrouper des tâches en fonction d’une colonne de la vue Liste. Par exemple, en double-cliquant sur le **état** en-tête de colonne, puis cliquez sur **Grouper par état**, vous pouvez regrouper toutes les tâches qui ont le même état. Par exemple, vous pouvez visualiser rapidement les tâches en attente afin de vous concentrer sur la raison de leur blocage. Vous pouvez également réduire un groupe qui ne présente pas d‘intérêt pour la session de débogage. De la même manière, vous pouvez regrouper les tâches en fonction des autres colonnes. Pour ajouter un indicateur à un groupe (ou en supprimer un), il suffit de cliquer sur le bouton en regard de l'en-tête de groupe. L’illustration suivante présente la fenêtre **Tâches** en mode regroupé.  
  
 ![Mode groupé dans la fenêtre Tâches parallèles](../debugger/media/parallel-tasks-groupedmode.png "Parallel_Tasks_GroupedMode")  
  
## <a name="parent-child-view"></a>Vue Parent enfant  
 (cette vue est uniquement disponible pour le code managé) En double-cliquant sur un en-tête de colonne, puis sur **Vue Parent enfant**, vous pouvez modifier la liste des tâches pour une vue hiérarchique, dans les enfants de chaque tâche est un sous-nœud qui peut être affiché ou masqué sous son parent. L'illustration suivante présente les tâches au sein de la vue parent-enfant.  
  
 ![Parent&#45;vue enfant dans la fenêtre Tâches parallèles](../debugger/media/parallel-tasks-parentchildview.png "Parallel_Tasks_ParentChildView")  
  
## <a name="flagging-tasks"></a>Ajout d'indicateurs à des tâches  
 Vous pouvez marquer le thread de la tâche sur lequel une tâche est en cours d’exécution en sélectionnant la tâche liste élément, puis en choisissant **indicateur** dans le menu contextuel ou en cliquant sur l’icône d’indicateur dans la première colonne. Si vous signalez plusieurs tâches, vous pouvez ensuite effectuer un tri sur la colonne d'indicateur pour déplacer toutes les tâches avec indicateur vers le haut afin de pouvoir vous concentrer uniquement sur celles-ci. Vous pouvez également utiliser la fenêtre **Piles parallèles** pour afficher uniquement les tâches avec indicateur. Cela vous permet d'éliminer par filtrage les tâches qui ne vous intéressent pas pour le débogage. Les indicateurs ne sont pas persistants entre les sessions de débogage.  
  
## <a name="freezing-and-thawing-tasks"></a>Gel et libération des tâches  
 Vous pouvez geler le thread sur lequel une tâche s’exécute en cliquant avec le bouton droit sur la tâche, puis en cliquant sur **Verrouiller le thread affecté**. (Si une tâche est déjà gelée, la commande s’intitule **Libérer le thread affecté**.) Lorsque vous gelez un thread, celui-ci ne s'exécute pas lorsque vous parcourez le code après le point d'arrêt actuel. Le **figer tous les Threads sauf celui-ci** commande gèle tous les threads sauf celui qui exécute la tâche.  
  
 L’illustration suivante présente les autres éléments de menu pour chaque tâche.  
  
 ![Menu contextuel du thread dans la fenêtre Tâches parallèles](../debugger/media/parallel-tasks-contextmenu2.png "Parallel_Tasks_ContextMenu2")  
  
## <a name="see-also"></a>Voir aussi  
 [Principes de base du débogueur](../debugger/debugger-basics.md)   
 [Débogage du code managé](../debugger/debugging-managed-code.md)   
 [Programmation parallèle](https://msdn.microsoft.com/library/4d83c690-ad2d-489e-a2e0-b85b898a672d)   
 [Runtime d’accès concurrentiel](https://msdn.microsoft.com/library/874bc58f-8dce-483e-a3a1-4dcc9e52ed2c)   
 [Utilisation de la fenêtre Piles parallèles](../debugger/using-the-parallel-stacks-window.md)   
 [Procédure pas à pas : Débogage d'une application parallèle](../debugger/walkthrough-debugging-a-parallel-application.md)
