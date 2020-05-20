---
title: начало работы Tutorial2
description: В этой статье приводятся руководства по программированию Windows Workflow Foundation приложений.
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 148ba77231067bf5f8ff1d8b444b83d951ce8761
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419854"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="cbc67-103">Учебник по началу работы</span><span class="sxs-lookup"><span data-stu-id="cbc67-103">Getting Started Tutorial</span></span>
<span data-ttu-id="cbc67-104">Этот раздел содержит набор пошаговых руководств, в которых представлены сведения о программировании приложений Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="cbc67-104">This section contains a set of walkthrough topics that introduce you to programming Windows Workflow Foundation (WF) applications.</span></span> <span data-ttu-id="cbc67-105">Следуя инструкциям, приведенным в данных разделах, вы сможете построить приложение, реализующее игру по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="cbc67-105">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="cbc67-106">В первом разделе учебника описаны шаги по созданию пользовательских действий, необходимых для рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="cbc67-106">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="cbc67-107">Во втором разделе выполняется сборка этих действий вместе со встроенными действиями рабочих процессов в рабочий процесс блок-схемы.</span><span class="sxs-lookup"><span data-stu-id="cbc67-107">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="cbc67-108">В третьем разделе выполняется настройка ведущего приложения для выполнения рабочего процесса, а в последнем разделе описывается сохраняемость.</span><span class="sxs-lookup"><span data-stu-id="cbc67-108">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="cbc67-109">Каждый шаг этого процесса зависит от предыдущих, поэтому рекомендуется выполнять их по порядку.</span><span class="sxs-lookup"><span data-stu-id="cbc67-109">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cbc67-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="cbc67-110">In This Section</span></span>  
 [<span data-ttu-id="cbc67-111">Практическое руководство. Создание действия</span><span class="sxs-lookup"><span data-stu-id="cbc67-111">How to: Create an Activity</span></span>](how-to-create-an-activity.md)  
 <span data-ttu-id="cbc67-112">Описывает способ создания настраиваемого действия, которое является производным от <xref:System.Activities.NativeActivity%601>, и способы формирования составного действия из этого и встроенного действия с помощью конструктора действий.</span><span class="sxs-lookup"><span data-stu-id="cbc67-112">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="cbc67-113">Практическое руководство. Создание рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cbc67-113">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)  
 <span data-ttu-id="cbc67-114">Описывает создание рабочих процессов блок-схем, последовательностей и конечных автоматов с помощью встроенных действий и пользовательских действий из предыдущего учебника.</span><span class="sxs-lookup"><span data-stu-id="cbc67-114">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="cbc67-115">Практическое руководство. Запуск рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cbc67-115">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)  
 <span data-ttu-id="cbc67-116">Описывает вызов рабочего процесса из среды узла и из рабочего процесса, а также возобновление закладок.</span><span class="sxs-lookup"><span data-stu-id="cbc67-116">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="cbc67-117">Практическое руководство. Создание и запуск длительного рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cbc67-117">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="cbc67-118">Описывает способы добавления сохраняемости к приложению рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cbc67-118">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="cbc67-119">Практическое руководство. Создание настраиваемого участника отслеживания</span><span class="sxs-lookup"><span data-stu-id="cbc67-119">How to: Create a Custom Tracking Participant</span></span>](how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="cbc67-120">Описывает процесс создания настраиваемого участника отслеживания и профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="cbc67-120">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="cbc67-121">Практическое руководство. Параллельное размещение множества версий рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cbc67-121">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="cbc67-122">Описывает, как использовать `WorkflowIdentity` для параллельного размещения нескольких версий рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cbc67-122">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="cbc67-123">Практическое руководство. Обновление определения выполняющегося экземпляра рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cbc67-123">How to: Update the Definition of a Running Workflow Instance</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="cbc67-124">Описывает, как использовать динамическое обновление для изменения выполняемых экземпляров рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="cbc67-124">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc67-125">См. также статью</span><span class="sxs-lookup"><span data-stu-id="cbc67-125">See also</span></span>

- [<span data-ttu-id="cbc67-126">Программирование в Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="cbc67-126">Windows Workflow Foundation Programming</span></span>](programming.md)
