---
title: Настройка проверки действий
ms.date: 03/30/2017
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
ms.openlocfilehash: c3e10fc096b16ef2cf7a6c7533ac9bad8c5ec205
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288961"
---
# <a name="configuring-activity-validation"></a><span data-ttu-id="2b193-102">Настройка проверки действий</span><span class="sxs-lookup"><span data-stu-id="2b193-102">Configuring Activity Validation</span></span>

<span data-ttu-id="2b193-103">Проверка действия позволяет авторам и пользователям действий выявлять ошибки и сообщать о них в конфигурации любого действия до его выполнения.</span><span class="sxs-lookup"><span data-stu-id="2b193-103">Activity validation enables activity authors and users to identify and report errors in an activity’s configuration prior to its execution.</span></span> <span data-ttu-id="2b193-104">Windows Workflow Foundation (WF) предоставляет следующие три типа проверки действий:</span><span class="sxs-lookup"><span data-stu-id="2b193-104">Windows Workflow Foundation (WF) provides the following three types of activity validation:</span></span>  
  
- <span data-ttu-id="2b193-105">Атрибуты `RequiredArgument` и `OverloadGroup`.</span><span class="sxs-lookup"><span data-stu-id="2b193-105">`RequiredArgument` and `OverloadGroup` attributes.</span></span>  
  
- <span data-ttu-id="2b193-106">Императивная, основанная на коде проверка.</span><span class="sxs-lookup"><span data-stu-id="2b193-106">Imperative code-based validation.</span></span>  
  
- <span data-ttu-id="2b193-107">Декларативные ограничения.</span><span class="sxs-lookup"><span data-stu-id="2b193-107">Declarative constraints.</span></span>  
  
 <span data-ttu-id="2b193-108">Атрибуты `RequiredArgument` и `OverloadGroup` указывают, что определенные аргументы в действии являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="2b193-108">`RequiredArgument` and `OverloadGroup` attributes indicate that certain arguments on an activity are required.</span></span> <span data-ttu-id="2b193-109">Императивная, основанная на коде проверка предоставляет действию простой способ выполнения самопроверки, а декларативные ограничения позволяют выполнять проверку действия и его связи с рабочим процессом, содержащим это действие.</span><span class="sxs-lookup"><span data-stu-id="2b193-109">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and declarative constraints enable validation about the activity and its relationship with the containing workflow.</span></span> <span data-ttu-id="2b193-110">Если действие не настроено в соответствии с требованиями проверки, то возвращаются ошибки проверки и предупреждения.</span><span class="sxs-lookup"><span data-stu-id="2b193-110">If an activity is not configured properly according to the validation requirements, validation errors and warnings are returned.</span></span> <span data-ttu-id="2b193-111">Если рабочий процесс, содержащий действие, создан с использованием конструктора рабочих процессов, то все ошибки проверки и предупреждения отображаются в этом конструкторе.</span><span class="sxs-lookup"><span data-stu-id="2b193-111">If the containing workflow is created using the workflow designer, any validation errors and warnings are displayed in the designer.</span></span> <span data-ttu-id="2b193-112">Если рабочий процесс создан за пределами конструктора рабочих процессов, то все ошибки проверки возвращаются при вызове рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2b193-112">If the workflow is created outside of the workflow designer any validation errors are returned when the workflow is invoked.</span></span> <span data-ttu-id="2b193-113">Независимо от способа создания рабочего процесса, рабочий процесс, содержащий ошибки проверки, выполнен не будет.</span><span class="sxs-lookup"><span data-stu-id="2b193-113">Regardless of how the workflow was created, a workflow with validation errors is never allowed to execute.</span></span> <span data-ttu-id="2b193-114">В этом разделе представлены общие сведения об этих типах проверки действий и способах ее вызова.</span><span class="sxs-lookup"><span data-stu-id="2b193-114">This section provides an overview of these types of activity validation and how activity validation is invoked.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b193-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2b193-115">In This Section</span></span>  

 [<span data-ttu-id="2b193-116">Обязательные аргументы и группы перегруженных аргументов</span><span class="sxs-lookup"><span data-stu-id="2b193-116">Required Arguments and Overload Groups</span></span>](required-arguments-and-overload-groups.md)  
 <span data-ttu-id="2b193-117">Описывает процесс использования атрибутов `RequiredArgument` и `OverloadGroup` для выполнения проверки.</span><span class="sxs-lookup"><span data-stu-id="2b193-117">Describes how to use the `RequiredArgument` and `OverloadGroup` attributes to provide validation.</span></span>  
  
 [<span data-ttu-id="2b193-118">Принудительная проверка на уровне кода</span><span class="sxs-lookup"><span data-stu-id="2b193-118">Imperative Code-Based Validation</span></span>](imperative-code-based-validation.md)  
 <span data-ttu-id="2b193-119">Описывает процесс использования проверки на уровне коде для действий, основанных на <xref:System.Activities.CodeActivity> и <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="2b193-119">Describes how to use code-based validation for <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> based activities.</span></span>  
  
 [<span data-ttu-id="2b193-120">Декларативные ограничения</span><span class="sxs-lookup"><span data-stu-id="2b193-120">Declarative Constraints</span></span>](declarative-constraints.md)  
 <span data-ttu-id="2b193-121">Описывает процесс использования декларативных ограничений для выполнения проверки сложных действий.</span><span class="sxs-lookup"><span data-stu-id="2b193-121">Describes how to use declarative constraints to provide complex activity validation.</span></span>  
  
 [<span data-ttu-id="2b193-122">Вызов проверки действия</span><span class="sxs-lookup"><span data-stu-id="2b193-122">Invoking Activity Validation</span></span>](invoking-activity-validation.md)  
 <span data-ttu-id="2b193-123">Описывает процесс автоматического вызова проверки действия и способы явного вызова проверки.</span><span class="sxs-lookup"><span data-stu-id="2b193-123">Discusses when activity validation is invoked automatically and how to explicitly invoke validation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2b193-124">Справочник</span><span class="sxs-lookup"><span data-stu-id="2b193-124">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2b193-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2b193-125">Related Sections</span></span>
