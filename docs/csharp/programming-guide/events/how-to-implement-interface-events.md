---
title: Руководство по программированию на C#. Реализация событий интерфейса
description: Сведения о реализации событий интерфейса в классе. Изучите примеры кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: 153a2efa254bf2f2c81cec4b28a53207cdc4efe5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167552"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="d284d-104">Руководство по программированию на C#. Реализация событий интерфейса</span><span class="sxs-lookup"><span data-stu-id="d284d-104">How to implement interface events (C# Programming Guide)</span></span>

<span data-ttu-id="d284d-105">[Интерфейс](../../language-reference/keywords/interface.md) может объявлять [события](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="d284d-105">An [interface](../../language-reference/keywords/interface.md) can declare an [event](../../language-reference/keywords/event.md).</span></span> <span data-ttu-id="d284d-106">Следующий пример демонстрирует реализацию событий интерфейса в классе.</span><span class="sxs-lookup"><span data-stu-id="d284d-106">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="d284d-107">По сути правила остаются таким же, как при реализации любого метода или свойства интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d284d-107">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
## <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="d284d-108">Реализация событий интерфейса в классе</span><span class="sxs-lookup"><span data-stu-id="d284d-108">To implement interface events in a class</span></span>  
  
<span data-ttu-id="d284d-109">Объявите событие в классе и вызовите его, когда потребуется.</span><span class="sxs-lookup"><span data-stu-id="d284d-109">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
```csharp
namespace ImplementInterfaceEvents  
{  
    public interface IDrawingObject  
    {  
        event EventHandler ShapeChanged;  
    }  
    public class MyEventArgs : EventArgs
    {  
        // class members  
    }  
    public class Shape : IDrawingObject  
    {  
        public event EventHandler ShapeChanged;  
        void ChangeShape()  
        {  
            // Do something here before the event…  

            OnShapeChanged(new MyEventArgs(/*arguments*/));  

            // or do something here after the event.
        }  
        protected virtual void OnShapeChanged(MyEventArgs e)  
        {  
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a><span data-ttu-id="d284d-110">Пример</span><span class="sxs-lookup"><span data-stu-id="d284d-110">Example</span></span>  

<span data-ttu-id="d284d-111">Следующий пример демонстрирует обработку менее распространенной ситуации, в которой класс наследует от двух или более интерфейсов, каждый из которых имеет событие с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="d284d-111">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="d284d-112">Вам придется предоставить явную реализацию интерфейса по крайней мере для одного из этих событий.</span><span class="sxs-lookup"><span data-stu-id="d284d-112">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="d284d-113">Когда вы создаете для события явную реализацию интерфейса, нужно добавить еще и методы доступа `add` и `remove`.</span><span class="sxs-lookup"><span data-stu-id="d284d-113">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="d284d-114">Обычно они предоставляются компилятором, но в этой ситуации компилятор не сможет предоставить их.</span><span class="sxs-lookup"><span data-stu-id="d284d-114">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
<span data-ttu-id="d284d-115">Предоставляя собственные методы доступа, вы можете указать одно или разные события вашего класса, которые соответствуют этим двум событиям.</span><span class="sxs-lookup"><span data-stu-id="d284d-115">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="d284d-116">Например, если события должны инициироваться в разное время в соответствии со спецификациями интерфейса, можно связать каждое из них с отдельной реализацией в классе.</span><span class="sxs-lookup"><span data-stu-id="d284d-116">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="d284d-117">В следующем примере подписчики определяют, какое из событий `OnDraw` они получат, указывая ссылку на фигуру `IShape` или `IDrawingObject`.</span><span class="sxs-lookup"><span data-stu-id="d284d-117">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a><span data-ttu-id="d284d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d284d-118">See also</span></span>

- [<span data-ttu-id="d284d-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d284d-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d284d-120">События</span><span class="sxs-lookup"><span data-stu-id="d284d-120">Events</span></span>](./index.md)
- [<span data-ttu-id="d284d-121">Делегаты</span><span class="sxs-lookup"><span data-stu-id="d284d-121">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="d284d-122">Явная реализация интерфейса</span><span class="sxs-lookup"><span data-stu-id="d284d-122">Explicit Interface Implementation</span></span>](../interfaces/explicit-interface-implementation.md)
- [<span data-ttu-id="d284d-123">Практическое руководство. Создание событий базового класса в производных классах</span><span class="sxs-lookup"><span data-stu-id="d284d-123">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)
