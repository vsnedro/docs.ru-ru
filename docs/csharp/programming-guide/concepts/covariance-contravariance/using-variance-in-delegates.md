---
title: Использование вариативности в делегатах (C#)
description: Узнайте, как использовать вариативность в делегатах с помощью приведенных примеров кода ковариации и контрвариантности.
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 62b0555ee29c5e7d2ba0954a8949d61596122cc7
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105688"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="2cece-103">Использование вариативности в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="2cece-103">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="2cece-104">При назначении метода делегату *ковариация* и *контравариантость* обеспечивают гибкость сопоставления типа делегата с сигнатурой метода.</span><span class="sxs-lookup"><span data-stu-id="2cece-104">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="2cece-105">Ковариация позволяет методу иметь тип возвращаемого значения, степень наследования которого больше, чем указано в делегате.</span><span class="sxs-lookup"><span data-stu-id="2cece-105">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="2cece-106">Контравариантность позволяет использовать метод с типами параметров, степень наследования которых меньше, чем у типа делегата.</span><span class="sxs-lookup"><span data-stu-id="2cece-106">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="2cece-107">Пример 1. Ковариантность</span><span class="sxs-lookup"><span data-stu-id="2cece-107">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="2cece-108">Описание</span><span class="sxs-lookup"><span data-stu-id="2cece-108">Description</span></span>  
 <span data-ttu-id="2cece-109">В этом примере демонстрируется использование делегатов с методами, типы возвращаемых значений которых являются производными от типа возвращаемого значения в сигнатуре делегата.</span><span class="sxs-lookup"><span data-stu-id="2cece-109">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="2cece-110">Тип данных, возвращаемый `DogsHandler`, является типом `Dogs`, производным от определенного в делегате типа `Mammals`.</span><span class="sxs-lookup"><span data-stu-id="2cece-110">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2cece-111">Код</span><span class="sxs-lookup"><span data-stu-id="2cece-111">Code</span></span>  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="2cece-112">Пример 2: Контрвариантность</span><span class="sxs-lookup"><span data-stu-id="2cece-112">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="2cece-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2cece-113">Description</span></span>

<span data-ttu-id="2cece-114">В этом примере демонстрируется использование делегатов с методами, параметры типа которых являются базовыми типами типа параметра сигнатуры делегата.</span><span class="sxs-lookup"><span data-stu-id="2cece-114">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="2cece-115">Контравариантность позволяет использовать один обработчик событий вместо нескольких.</span><span class="sxs-lookup"><span data-stu-id="2cece-115">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="2cece-116">В следующем примере используется два делегата:</span><span class="sxs-lookup"><span data-stu-id="2cece-116">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="2cece-117">Делегат <xref:System.Windows.Forms.KeyEventHandler>, определяющий сигнатуру события [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown).</span><span class="sxs-lookup"><span data-stu-id="2cece-117">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="2cece-118">Его сигнатура:</span><span class="sxs-lookup"><span data-stu-id="2cece-118">Its signature is:</span></span>

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- <span data-ttu-id="2cece-119">Делегат <xref:System.Windows.Forms.MouseEventHandler>, определяющий сигнатуру события [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown).</span><span class="sxs-lookup"><span data-stu-id="2cece-119">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="2cece-120">Его сигнатура:</span><span class="sxs-lookup"><span data-stu-id="2cece-120">Its signature is:</span></span>

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

<span data-ttu-id="2cece-121">В примере определяется обработчик событий с параметром <xref:System.EventArgs>, который используется для обработки событий `Button.KeyDown` и `Button.MouseClick`.</span><span class="sxs-lookup"><span data-stu-id="2cece-121">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="2cece-122">Это можно сделать, поскольку <xref:System.EventArgs> является базовым типом <xref:System.Windows.Forms.KeyEventArgs> и <xref:System.Windows.Forms.MouseEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="2cece-122">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>
  
### <a name="code"></a><span data-ttu-id="2cece-123">Код</span><span class="sxs-lookup"><span data-stu-id="2cece-123">Code</span></span>  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cece-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2cece-124">See also</span></span>

- [<span data-ttu-id="2cece-125">Вариативность в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="2cece-125">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="2cece-126">Использование вариативности в универсальных методах-делегатах Func и Action (C#)</span><span class="sxs-lookup"><span data-stu-id="2cece-126">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
