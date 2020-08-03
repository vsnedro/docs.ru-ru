---
title: Руководство по программированию на C#. Свойства интерфейса
description: В C# можно объявлять свойства для интерфейса. Этот пример объявляет метод доступа к свойству интерфейса.
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 920381ae804a6a968bfd667171269377f3d7e448
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864973"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="6fe34-104">Свойства интерфейса (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="6fe34-104">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="6fe34-105">Свойства можно объявлять для [интерфейса](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="6fe34-105">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="6fe34-106">Следующий пример объявляет метод доступа к свойству интерфейса:</span><span class="sxs-lookup"><span data-stu-id="6fe34-106">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="6fe34-107">Свойства интерфейса обычно не имеют тела.</span><span class="sxs-lookup"><span data-stu-id="6fe34-107">Interface properties typically don't have a body.</span></span> <span data-ttu-id="6fe34-108">Методы доступа указывают, доступно ли свойство для чтения и записи, только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="6fe34-108">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="6fe34-109">В отличие от классов и структур, объявление методов доступа без тела не приводит к объявлению [автоматически реализуемого свойства](auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6fe34-109">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="6fe34-110">Начиная с C# 8.0 интерфейс может определять реализацию по умолчанию для членов, включая свойства.</span><span class="sxs-lookup"><span data-stu-id="6fe34-110">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="6fe34-111">Определение реализации по умолчанию для свойства в интерфейсе используется редко, так как интерфейсы могут не определять поля данных экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6fe34-111">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="6fe34-112">Пример</span><span class="sxs-lookup"><span data-stu-id="6fe34-112">Example</span></span>

<span data-ttu-id="6fe34-113">В этом примере интерфейс `IEmployee` содержит доступное для чтения и записи свойство `Name`, а также свойство `Counter`, предназначенное только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6fe34-113">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="6fe34-114">Класс `Employee` реализует интерфейс `IEmployee` и использует эти два свойства.</span><span class="sxs-lookup"><span data-stu-id="6fe34-114">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="6fe34-115">Программа считывает имя нового сотрудника и текущее число сотрудников, после чего отображает имя сотрудника и его рассчитанный номер.</span><span class="sxs-lookup"><span data-stu-id="6fe34-115">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="6fe34-116">Вы можете использовать полное имя свойства, которое ссылается на интерфейс, где был объявлен член.</span><span class="sxs-lookup"><span data-stu-id="6fe34-116">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="6fe34-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="6fe34-117">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="6fe34-118">В предыдущем примере показана [явная реализация интерфейса](../interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="6fe34-118">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="6fe34-119">Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых содержат свойство `Name`, потребуется явная реализация члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6fe34-119">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="6fe34-120">Это значит, что потребуется следующее объявление свойства:</span><span class="sxs-lookup"><span data-stu-id="6fe34-120">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="6fe34-121">реализует свойство `Name` в интерфейсе `IEmployee`, тогда как следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="6fe34-121">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="6fe34-122">реализует свойство `Name` в интерфейсе `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="6fe34-122">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="6fe34-123">Пример полученных результатов</span><span class="sxs-lookup"><span data-stu-id="6fe34-123">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="6fe34-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6fe34-124">See also</span></span>

- [<span data-ttu-id="6fe34-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6fe34-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6fe34-126">Свойства</span><span class="sxs-lookup"><span data-stu-id="6fe34-126">Properties</span></span>](./properties.md)
- [<span data-ttu-id="6fe34-127">Использование свойств</span><span class="sxs-lookup"><span data-stu-id="6fe34-127">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="6fe34-128">Сравнение свойств и индексаторов</span><span class="sxs-lookup"><span data-stu-id="6fe34-128">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="6fe34-129">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="6fe34-129">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="6fe34-130">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6fe34-130">Interfaces</span></span>](../interfaces/index.md)
