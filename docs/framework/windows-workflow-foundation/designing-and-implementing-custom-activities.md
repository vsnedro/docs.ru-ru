---
title: Разработка и реализация настраиваемых действий
description: В этой статье содержатся ресурсы для создания настраиваемых действий в Workflow Foundation путем создания составных действий или создания новых типов действий.
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 9c184bff9518bb5581f3bf4cd408db224736192b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419997"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="94315-103">Разработка и реализация настраиваемых действий</span><span class="sxs-lookup"><span data-stu-id="94315-103">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="94315-104">Настраиваемые действия в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] создаются либо посредством сборки системных действий в составные действия, либо путем создания новых типов, производных от <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> или <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="94315-104">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="94315-105">В этом разделе описываются способы создания пользовательских действий обоими способами.</span><span class="sxs-lookup"><span data-stu-id="94315-105">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="94315-106">Настраиваемые действия по умолчанию отображаются в конструкторе рабочих процессов в виде простого прямоугольника с именем действия.</span><span class="sxs-lookup"><span data-stu-id="94315-106">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="94315-107">Для создания настраиваемого визуального представления действия в конструкторе рабочих процессов также необходимо создать пользовательский конструктор.</span><span class="sxs-lookup"><span data-stu-id="94315-107">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="94315-108">Дополнительные сведения см. [в разделе Использование настраиваемых конструкторов действий и шаблонов](using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="94315-108">For more information, see [Using Custom Activity Designers and Templates](using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94315-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="94315-109">In This Section</span></span>  
 [<span data-ttu-id="94315-110">Параметры разработки действий</span><span class="sxs-lookup"><span data-stu-id="94315-110">Activity Authoring Options</span></span>](activity-authoring-options-in-wf.md)  
 <span data-ttu-id="94315-111">Описывает стили разработки, доступные в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94315-111">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="94315-112">Применение пользовательского действия</span><span class="sxs-lookup"><span data-stu-id="94315-112">Using a custom activity</span></span>](using-a-custom-activity.md)  
 <span data-ttu-id="94315-113">Описывает, как добавить пользовательское действие в проект рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="94315-113">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="94315-114">Создание асинхронных действий</span><span class="sxs-lookup"><span data-stu-id="94315-114">Creating Asynchronous Activities</span></span>](creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="94315-115">Описывает создание асинхронных действий.</span><span class="sxs-lookup"><span data-stu-id="94315-115">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="94315-116">Настройка проверки действий</span><span class="sxs-lookup"><span data-stu-id="94315-116">Configuring Activity Validation</span></span>](configuring-activity-validation.md)  
 <span data-ttu-id="94315-117">Описывает, как проверка действия может быть использована для выявления ошибок в конфигурации действия до его выполнения.</span><span class="sxs-lookup"><span data-stu-id="94315-117">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="94315-118">Создание действия в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="94315-118">Creating an Activity at Runtime</span></span>](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="94315-119">Описывает, как создавать действия во время выполнения с помощью <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="94315-119">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="94315-120">Свойства выполнения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="94315-120">Workflow Execution Properties</span></span>](workflow-execution-properties.md)  
 <span data-ttu-id="94315-121">Описывает, как использовать свойства выполнения рабочего процесса для добавления определенных свойств контекста к среде действия.</span><span class="sxs-lookup"><span data-stu-id="94315-121">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="94315-122">Использование делегатов действий</span><span class="sxs-lookup"><span data-stu-id="94315-122">Using Activity Delegates</span></span>](using-activity-delegates.md)  
 <span data-ttu-id="94315-123">Описывает создание и использование действий, содержащих делегаты действий.</span><span class="sxs-lookup"><span data-stu-id="94315-123">Discusses how to author and use activities that contain activity delegates.</span></span>
  
 [<span data-ttu-id="94315-124">Использование модулей действий</span><span class="sxs-lookup"><span data-stu-id="94315-124">Using Activity Extensions</span></span>](using-activity-extensions.md)  
 <span data-ttu-id="94315-125">Описывает, как создавать и использовать расширения действий.</span><span class="sxs-lookup"><span data-stu-id="94315-125">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="94315-126">Использование каналов OData из рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="94315-126">Consuming OData Feeds from a Workflow</span></span>](consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="94315-127">Описывает различные методы для вызова службы данных WCF из рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="94315-127">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="94315-128">Определение области и видимости действия</span><span class="sxs-lookup"><span data-stu-id="94315-128">Activity Definition Scoping and Visibility</span></span>](activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="94315-129">Описывает параметры и правила для определения области данных и видимости элементов для действий.</span><span class="sxs-lookup"><span data-stu-id="94315-129">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
