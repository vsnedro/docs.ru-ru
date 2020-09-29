---
title: Руководство по программированию на C#. Порождение событий базового класса в производных классах
description: Сведения о создании событий базового класса в производных классах. Изучите пример кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: b9708876e7d46072439ae498fd551a7b3b23a29e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167526"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="050c7-104">Руководство по программированию на C#. Порождение событий базового класса в производных классах</span><span class="sxs-lookup"><span data-stu-id="050c7-104">How to raise base class events in derived classes (C# Programming Guide)</span></span>

<span data-ttu-id="050c7-105">В следующем простом примере показан стандартный способ объявления событий в базовом классе, позволяющий вызывать их из производных классов.</span><span class="sxs-lookup"><span data-stu-id="050c7-105">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="050c7-106">Этот шаблон активно применяется в классах Windows Forms в библиотеке классов .NET.</span><span class="sxs-lookup"><span data-stu-id="050c7-106">This pattern is used extensively in Windows Forms classes in the .NET class libraries.</span></span>  
  
 <span data-ttu-id="050c7-107">При создании класса, который можно использовать в качестве базового для других классов, следует учитывать тот факт, что события представляют собой особый тип делегатов, который может вызываться только в том классе, который их объявил.</span><span class="sxs-lookup"><span data-stu-id="050c7-107">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="050c7-108">Производные классы не могут создавать события, объявленные в базовом классе, напрямую.</span><span class="sxs-lookup"><span data-stu-id="050c7-108">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="050c7-109">Несмотря на то, что в некоторых обстоятельствах вам может потребоваться событие, вызываемое только базовым классом, в большинстве случаев рекомендуется разрешать производному классу вызывать события базового класса.</span><span class="sxs-lookup"><span data-stu-id="050c7-109">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="050c7-110">Для этого следует создать в базовом классе защищенный метод, предоставляющий оболочку для события.</span><span class="sxs-lookup"><span data-stu-id="050c7-110">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="050c7-111">Вызывая или перезаписывая вызывающий метод, производные классы могут вызывать событие косвенно.</span><span class="sxs-lookup"><span data-stu-id="050c7-111">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="050c7-112">Не объявляйте виртуальные события в базовом классе и не переопределяйте их в производном классе.</span><span class="sxs-lookup"><span data-stu-id="050c7-112">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="050c7-113">Компилятор c# не обрабатывает их корректно, поэтому сложно сказать, будет ли подписчик производного события на самом деле подписываться на событие базового класса.</span><span class="sxs-lookup"><span data-stu-id="050c7-113">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="050c7-114">Пример</span><span class="sxs-lookup"><span data-stu-id="050c7-114">Example</span></span>  

 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="050c7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="050c7-115">See also</span></span>

- [<span data-ttu-id="050c7-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="050c7-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="050c7-117">События</span><span class="sxs-lookup"><span data-stu-id="050c7-117">Events</span></span>](./index.md)
- [<span data-ttu-id="050c7-118">Делегаты</span><span class="sxs-lookup"><span data-stu-id="050c7-118">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="050c7-119">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="050c7-119">Access Modifiers</span></span>](../classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="050c7-120">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="050c7-120">Creating Event Handlers in Windows Forms</span></span>](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms)
