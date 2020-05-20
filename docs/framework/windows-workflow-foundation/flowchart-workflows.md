---
title: Рабочие процессы блок-схемы
description: В этой статье описывается действие блок-схемы, которое обычно используется для реализации непоследовательных рабочих процессов в Workflow Foundation.
ms.date: 03/30/2017
ms.assetid: b0a3475c-d22f-49eb-8912-973c960aebf5
ms.openlocfilehash: ce0661653a1d50b3f7264246b810faabbd12bf5f
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419919"
---
# <a name="flowchart-workflows"></a><span data-ttu-id="ce48b-103">Рабочие процессы блок-схемы</span><span class="sxs-lookup"><span data-stu-id="ce48b-103">Flowchart Workflows</span></span>

<span data-ttu-id="ce48b-104">Блок-схемы лежат в основе широко известного принципа разработки программ.</span><span class="sxs-lookup"><span data-stu-id="ce48b-104">A flowchart is a well-known paradigm for designing programs.</span></span> <span data-ttu-id="ce48b-105">Действие «Блок-схема» обычно используется для реализации непоследовательных рабочих процессов, но если не требуются узлы `FlowDecision`, то может использоваться для реализации последовательных рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="ce48b-105">The Flowchart activity is typically used to implement non-sequential workflows, but can be used for sequential workflows if no `FlowDecision` nodes are used.</span></span>

## <a name="flowchart-workflow-structure"></a><span data-ttu-id="ce48b-106">Структура рабочего процесса блок-схемы</span><span class="sxs-lookup"><span data-stu-id="ce48b-106">Flowchart workflow structure</span></span>

 <span data-ttu-id="ce48b-107">Действие Flowchart представляет собой действие, содержащее набор действий, которые будут выполнены.</span><span class="sxs-lookup"><span data-stu-id="ce48b-107">A Flowchart activity is an activity that contains a collection of activities to be executed.</span></span>  <span data-ttu-id="ce48b-108">Блок-схемы также содержат элементы управления потоком, такие как <xref:System.Activities.Statements.FlowDecision> и <xref:System.Activities.Statements.FlowSwitch%601>, контролирующие выполнение между содержащимися действиями на основании значений переменных.</span><span class="sxs-lookup"><span data-stu-id="ce48b-108">Flowcharts also contain flow control elements such as <xref:System.Activities.Statements.FlowDecision> and <xref:System.Activities.Statements.FlowSwitch%601> that direct execution between contained activities based on the values of variables.</span></span>

## <a name="types-of-flow-nodes"></a><span data-ttu-id="ce48b-109">Типы узлов потока</span><span class="sxs-lookup"><span data-stu-id="ce48b-109">Types of flow nodes</span></span>

 <span data-ttu-id="ce48b-110">Используются различные типы элементов в зависимости от типа управления потока, требуемого при выполнении элемента.</span><span class="sxs-lookup"><span data-stu-id="ce48b-110">Different types of elements are used depending on the type of flow control required when the element executes.</span></span> <span data-ttu-id="ce48b-111">К типам элементов блок-схемы относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="ce48b-111">Types of flowchart elements include:</span></span>

- <span data-ttu-id="ce48b-112">`FlowStep` - моделирует один шаг выполнения в блок-схеме.</span><span class="sxs-lookup"><span data-stu-id="ce48b-112">`FlowStep` - Models one step of execution in the flowchart.</span></span>

- <span data-ttu-id="ce48b-113">`FlowDecision` - создает ветвь выполнения на основе логического условия, такого как <xref:System.Activities.Statements.If>.</span><span class="sxs-lookup"><span data-stu-id="ce48b-113">`FlowDecision` - Branches execution based on a Boolean condition, similar to <xref:System.Activities.Statements.If>.</span></span>

- <span data-ttu-id="ce48b-114">`FlowSwitch` - обеспечивает ветвление в ходе выполнения на основе переключателя с неперекрывающимися ветвями, такого как <xref:System.Activities.Statements.Switch%601>.</span><span class="sxs-lookup"><span data-stu-id="ce48b-114">`FlowSwitch` – Branches execution based on an exclusive switch, similar to <xref:System.Activities.Statements.Switch%601>.</span></span>

<span data-ttu-id="ce48b-115">Каждая ссылка имеет свойство `Action`, определяющее действие <xref:System.Activities.ActivityAction>, которое может быть использовано для выполнения дочерних действий, а также одно или несколько свойств `Next`, которые определяют элемент или элементы, выполняемые после завершения выполнения текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="ce48b-115">Each link has an `Action` property that defines a <xref:System.Activities.ActivityAction> that can be used to execute child activities, and one or more `Next` properties that define which element or elements to execute when the current element finishes execution.</span></span>

### <a name="creating-a-basic-activity-sequence-with-a-flowstep-node"></a><span data-ttu-id="ce48b-116">Создание базовой последовательности действий с Фловстеп узлом</span><span class="sxs-lookup"><span data-stu-id="ce48b-116">Creating a basic activity sequence with a FlowStep node</span></span>

<span data-ttu-id="ce48b-117">Для моделирования базовой последовательности, в которой поочередно выполняются два действия, используется элемент `FlowStep`.</span><span class="sxs-lookup"><span data-stu-id="ce48b-117">To model a basic sequence in which two activities execute in turn, the `FlowStep` element is used.</span></span> <span data-ttu-id="ce48b-118">В следующем примере используются два элемента `FlowStep` для последовательного выполнения двух действий.</span><span class="sxs-lookup"><span data-stu-id="ce48b-118">In the following example, two `FlowStep` elements are used to execute two activities in sequence.</span></span>

```xml
<Flowchart>
  <FlowStep>
    <Assign DisplayName="Get Name">
      <Assign.To>
        <OutArgument x:TypeArguments="x:String">[result]</OutArgument>
      </Assign.To>
      <Assign.Value>
        <InArgument x:TypeArguments="x:String">["User"]</InArgument>
      </Assign.Value>
    </Assign>
    <FlowStep.Next>
      <FlowStep>
        <WriteLine Text="Hello, " & [result]/>
      </FlowStep>
    </FlowStep.Next>
  </FlowStep>
</Flowchart>
```

### <a name="creating-a-conditional-flowchart-with-a-flowdecision-node"></a><span data-ttu-id="ce48b-119">Создание условной блок-схемы с FlowDecision узлом</span><span class="sxs-lookup"><span data-stu-id="ce48b-119">Creating a conditional flowchart with a FlowDecision node</span></span>

<span data-ttu-id="ce48b-120">Чтобы смоделировать узел условного потока на блок-схеме рабочего процесса (т. е. создать ссылку, работающую аналогично символу принятия решения на стандартной блок-схеме), следует использовать узел <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="ce48b-120">To model a conditional flow node in a flowchart workflow (that is, to create a link that functions as a traditional flowchart's decision symbol), a <xref:System.Activities.Statements.FlowDecision> node is used.</span></span> <span data-ttu-id="ce48b-121">Для свойства <xref:System.Activities.Statements.FlowDecision.Condition%2A> узла задано выражение, которое определяет условие, а для свойств <xref:System.Activities.Statements.FlowDecision.True%2A> и <xref:System.Activities.Statements.FlowDecision.False%2A> заданы экземпляры <xref:System.Activities.Statements.FlowNode>, которые будут выполняться, если результатом вычисления выражения будет `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="ce48b-121">The <xref:System.Activities.Statements.FlowDecision.Condition%2A> property of the node is set to an expression that defines the condition, and the <xref:System.Activities.Statements.FlowDecision.True%2A> and <xref:System.Activities.Statements.FlowDecision.False%2A> properties are set to <xref:System.Activities.Statements.FlowNode> instances to be executed if the expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="ce48b-122">В следующем примере показано определение рабочего процесса, который использует узел <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="ce48b-122">The following example shows how to define a workflow that uses a <xref:System.Activities.Statements.FlowDecision> node.</span></span>

```xml
<Flowchart>
  <FlowStep>
    <Read Result="[s]"/>
    <FlowStep.Next>
      <FlowDecision>
        <IsEmpty Input="[s]" />
        <FlowDecision.True>
          <FlowStep>
            <Write Text="Empty"/>
          </FlowStep>
        </FlowDecision.True>
        <FlowDecision.False>
          <FlowStep>
            <Write Text="Non-Empty"/>
          </FlowStep>
        </FlowDecision.False>
      </FlowDecision>
    </FlowStep.Next>
  </FlowStep>
</Flowchart>
```

### <a name="creating-an-exclusive-switch-with-a-flowswitch-node"></a><span data-ttu-id="ce48b-123">Создание монопольного ключа с узлом FlowSwitch</span><span class="sxs-lookup"><span data-stu-id="ce48b-123">Creating an exclusive switch with a FlowSwitch node</span></span>

<span data-ttu-id="ce48b-124">Чтобы смоделировать блок-схему, в которой на основе соответствующего значения выбирается один из взаимоисключающих вариантов пути, используется узел <xref:System.Activities.Statements.FlowSwitch%601>.</span><span class="sxs-lookup"><span data-stu-id="ce48b-124">To model a flowchart in which one exclusive path is selected based on a matching value, the <xref:System.Activities.Statements.FlowSwitch%601> node is used.</span></span> <span data-ttu-id="ce48b-125">Свойство <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> имеет значение <xref:System.Activities.Activity%601> с параметром типа <xref:System.Object>, который определяет значение для сопоставления с выбираемыми элементами.</span><span class="sxs-lookup"><span data-stu-id="ce48b-125">The <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> property is set to a <xref:System.Activities.Activity%601> with a type parameter of <xref:System.Object> that defines the value to match choices against.</span></span> <span data-ttu-id="ce48b-126">Свойство <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> определяет словарь ключей и объектов <xref:System.Activities.Statements.FlowNode> для сопоставления с условным выражением и набор объектов <xref:System.Activities.Statements.FlowNode>, которые определяют направление выполнения в случае, если заданный вариант соответствует условному выражению.</span><span class="sxs-lookup"><span data-stu-id="ce48b-126">The <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> property defines a dictionary of keys and <xref:System.Activities.Statements.FlowNode> objects to match against the conditional expression, and a set of <xref:System.Activities.Statements.FlowNode> objects that define how execution should flow if the given case matches the conditional expression.</span></span> <span data-ttu-id="ce48b-127"><xref:System.Activities.Statements.FlowSwitch%601> также определяет свойство <xref:System.Activities.Statements.FlowSwitch%601.Default%2A>, которое определяет направление выполнения при отсутствии соответствий условному выражению.</span><span class="sxs-lookup"><span data-stu-id="ce48b-127">The <xref:System.Activities.Statements.FlowSwitch%601> also defines a <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> property that defines how execution should flow if no cases match the condition expression.</span></span> <span data-ttu-id="ce48b-128">В следующем примере показано, как определить рабочий процесс, который использует элемент <xref:System.Activities.Statements.FlowSwitch%601>.</span><span class="sxs-lookup"><span data-stu-id="ce48b-128">The following example demonstrates how to define a workflow that uses a <xref:System.Activities.Statements.FlowSwitch%601> element.</span></span>

```xml
<Flowchart>
  <FlowSwitch>
    <FlowStep x:Key="Red">
      <WriteRed/>
    </FlowStep>
    <FlowStep x:Key="Blue">
      <WriteBlue/>
    </FlowStep>
    <FlowStep x:Key="Green">
      <WriteGreen/>
    </FlowStep>
  </FlowSwitch>
</Flowchart>
```
