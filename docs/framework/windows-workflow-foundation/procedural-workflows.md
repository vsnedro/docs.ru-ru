---
title: Процедурные рабочие процессы
description: В Workflow Foundation процедурные рабочие процессы используют методы управления потоком, аналогичные тем, что имеются в процедурных языках.
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 97664c1352928e7d05c2ed15fc118dd21474cfc3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421440"
---
# <a name="procedural-workflows"></a><span data-ttu-id="dfc05-103">Процедурные рабочие процессы</span><span class="sxs-lookup"><span data-stu-id="dfc05-103">Procedural Workflows</span></span>
<span data-ttu-id="dfc05-104">Процедурные рабочие процессы используют методы управления потоком выполнения, аналогичные таким методам в процедурных языках.</span><span class="sxs-lookup"><span data-stu-id="dfc05-104">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="dfc05-105">К этим конструкциям относятся `While` и `If`.</span><span class="sxs-lookup"><span data-stu-id="dfc05-105">These constructs include `While` and `If`.</span></span> <span data-ttu-id="dfc05-106">Такие рабочие процессы можно свободно создавать с применением других действий управления потоком выполнения, таких как <xref:System.Activities.Statements.Flowchart> и <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="dfc05-106">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="dfc05-107">Управление потоком выполнения</span><span class="sxs-lookup"><span data-stu-id="dfc05-107">Controlling Execution Flow</span></span>  
 <span data-ttu-id="dfc05-108">Библиотека действий рабочих процессов содержит действия для моделирования большинства методов управления потоком выполнения, используемых в процедурных языках.</span><span class="sxs-lookup"><span data-stu-id="dfc05-108">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="dfc05-109">К ним относятся:</span><span class="sxs-lookup"><span data-stu-id="dfc05-109">These include:</span></span>  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="dfc05-110">Чтобы использовать действия управления потоком, перетащите их из панели элементов **действия** в составное действие в окне конструктора.</span><span class="sxs-lookup"><span data-stu-id="dfc05-110">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dfc05-111">При использовании компонентов Windows Server AppFabric для размещения рабочих процессов на веб-ферме AppFabric переместит экземпляры между разными серверами AppFabric.</span><span class="sxs-lookup"><span data-stu-id="dfc05-111">If using the hosting features of Windows Server AppFabric to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="dfc05-112">Для этого необходимо, чтобы ресурсы можно было совместно использовать на всех узлах.</span><span class="sxs-lookup"><span data-stu-id="dfc05-112">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="dfc05-113">Ни одно из действий рабочих процессов .NET 4 по умолчанию не содержит операций, осуществляющих доступ к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="dfc05-113">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="dfc05-114">Поскольку AppFabric не реализует ни одного механизма пометки рабочего процесса как неперемещаемого, разработчику не следует создавать пользовательские действия, в которых возникает ошибка при перемещении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dfc05-114">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc05-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="dfc05-115">See also</span></span>

- [<span data-ttu-id="dfc05-116">Рабочие процессы блок-схемы</span><span class="sxs-lookup"><span data-stu-id="dfc05-116">Flowchart Workflows</span></span>](flowchart-workflows.md)
