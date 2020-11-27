---
title: Разработка действий рабочих процессов с помощью класса Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 21f1c8b1249d41029fa7a19360e96ad866c823a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293849"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="22b19-102">Разработка действий рабочих процессов с помощью класса Activity</span><span class="sxs-lookup"><span data-stu-id="22b19-102">Workflow Activity Authoring Using the Activity Class</span></span>

<span data-ttu-id="22b19-103">Самый простой способ создать действие с помощью Windows Workflow Foundation (WF) в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] — создать класс, который наследует от класса <xref:System.Activities.Activity> , который создает функциональные возможности путем сборки пользовательских действий или действий из [встроенной библиотеки действий](net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="22b19-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="22b19-104">В этом разделе показано, как создать действие для вывода двух сообщений на консоль.</span><span class="sxs-lookup"><span data-stu-id="22b19-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="22b19-105">Для создания пользовательского действия с помощью конструктора действий сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="22b19-105">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="22b19-106">Откройте Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="22b19-106">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="22b19-107">Выберите в меню «Файл» пункт «Создать», затем пункт «Создать проект».</span><span class="sxs-lookup"><span data-stu-id="22b19-107">Select File, New, Project.</span></span> <span data-ttu-id="22b19-108">Выберите **Рабочий процесс 4,0** в разделе **Visual C#** в окне **типы проектов** и выберите узел **v2010** .</span><span class="sxs-lookup"><span data-stu-id="22b19-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="22b19-109">В окне **шаблоны** выберите пункт **Библиотека действий** .</span><span class="sxs-lookup"><span data-stu-id="22b19-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="22b19-110">Задайте имя для нового проекта HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="22b19-110">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="22b19-111">Откройте окно создания нового действия.</span><span class="sxs-lookup"><span data-stu-id="22b19-111">Open the new activity.</span></span>  <span data-ttu-id="22b19-112">Перетащите действие <xref:System.Activities.Statements.Sequence> из области элементов в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="22b19-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="22b19-113">Перетащите действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> activity.</span><span class="sxs-lookup"><span data-stu-id="22b19-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="22b19-114">Введите `"Hello World"` (с кавычками) в **текстовое** поле.</span><span class="sxs-lookup"><span data-stu-id="22b19-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="22b19-115">Перетащите второе действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> под первым.</span><span class="sxs-lookup"><span data-stu-id="22b19-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="22b19-116">Введите `"Goodbye"` (с кавычками) в **текстовое** поле.</span><span class="sxs-lookup"><span data-stu-id="22b19-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
