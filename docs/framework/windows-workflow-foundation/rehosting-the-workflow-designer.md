---
title: Повторное размещение конструктора рабочих процессов
description: Конструктор рабочих процессов Windows можно повторно разместить в средах, находящихся за пределами Visual Studio, для создания, изменения и мониторинга рабочих процессов.
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 34709b84d445b2bb07e32bfd3f34d06072f125bf
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421427"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="2760d-103">Повторное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2760d-103">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="2760d-104">Конструктор рабочих процессов Windows можно повторно разместить в средах, находящихся за пределами Visual Studio 2012, в целях создания, изменения и мониторинга рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="2760d-104">The Windows Workflow Designer can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="2760d-105">Тип <xref:System.Activities.Presentation.WorkflowDesigner> представляет собой оболочку полотна, сетку свойств и другие элементы и обеспечивает базовую модель программирования для обработки большей части вариантов повторного размещения конструктора.</span><span class="sxs-lookup"><span data-stu-id="2760d-105">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="2760d-106">Размещение <xref:System.Activities.Presentation.WorkflowDesigner> внутри приложения Windows Presentation Foundation (WPF) — это распространенный сценарий повторного размещения для конструктор рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="2760d-106">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for Workflow Designer.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2760d-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2760d-107">In This Section</span></span>
 [<span data-ttu-id="2760d-108">Задача 1. Создание нового приложения Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="2760d-108">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="2760d-109">Задача 2. Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2760d-109">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="2760d-110">Задача 3. Создание области элементов и сетки свойств</span><span class="sxs-lookup"><span data-stu-id="2760d-110">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="2760d-111">Поддержка новых возможностей Workflow Foundation 4.5 во вновь размещенном конструкторе рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2760d-111">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="2760d-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="2760d-112">See also</span></span>

- [<span data-ttu-id="2760d-113">Рекомендации по настройке конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2760d-113">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
