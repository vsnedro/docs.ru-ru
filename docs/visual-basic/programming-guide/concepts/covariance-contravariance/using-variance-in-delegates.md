---
title: Использование вариативности в делегатах
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: 842392a1342f7d3689d4d1f2a2adb7470eeda05e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375788"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="2ed29-102">Использование вариативности в делегатах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ed29-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="2ed29-103">При назначении метода делегату *ковариация* и *контравариантость* обеспечивают гибкость сопоставления типа делегата с сигнатурой метода.</span><span class="sxs-lookup"><span data-stu-id="2ed29-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="2ed29-104">Ковариация позволяет методу иметь тип возвращаемого значения, степень наследования которого больше, чем указано в делегате.</span><span class="sxs-lookup"><span data-stu-id="2ed29-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="2ed29-105">Контравариантность позволяет использовать метод с типами параметров, степень наследования которых меньше, чем у типа делегата.</span><span class="sxs-lookup"><span data-stu-id="2ed29-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="2ed29-106">Пример 1. Ковариация</span><span class="sxs-lookup"><span data-stu-id="2ed29-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="2ed29-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="2ed29-107">Description</span></span>

<span data-ttu-id="2ed29-108">В этом примере демонстрируется использование делегатов с методами, типы возвращаемых значений которых являются производными от типа возвращаемого значения в сигнатуре делегата.</span><span class="sxs-lookup"><span data-stu-id="2ed29-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="2ed29-109">Тип данных, возвращаемый `DogsHandler`, является типом `Dogs`, производным от определенного в делегате типа `Mammals`.</span><span class="sxs-lookup"><span data-stu-id="2ed29-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="2ed29-110">Код</span><span class="sxs-lookup"><span data-stu-id="2ed29-110">Code</span></span>

```vb
Class Mammals
End Class

Class Dogs
    Inherits Mammals
End Class
Class Test
    Public Delegate Function HandlerMethod() As Mammals
    Public Shared Function MammalsHandler() As Mammals
        Return Nothing
    End Function
    Public Shared Function DogsHandler() As Dogs
        Return Nothing
    End Function
    Sub Test()
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler
        ' Covariance enables this assignment.
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler
    End Sub
End Class
```

## <a name="example-2-contravariance"></a><span data-ttu-id="2ed29-111">Пример 2. Контравариантность</span><span class="sxs-lookup"><span data-stu-id="2ed29-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="2ed29-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="2ed29-112">Description</span></span>

<span data-ttu-id="2ed29-113">В этом примере демонстрируется использование делегатов с методами, параметры типа которых являются базовыми типами типа параметра сигнатуры делегата.</span><span class="sxs-lookup"><span data-stu-id="2ed29-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="2ed29-114">Контравариантность позволяет использовать один обработчик событий вместо нескольких.</span><span class="sxs-lookup"><span data-stu-id="2ed29-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="2ed29-115">В следующем примере используется два делегата:</span><span class="sxs-lookup"><span data-stu-id="2ed29-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="2ed29-116">Делегат <xref:System.Windows.Forms.KeyEventHandler>, определяющий сигнатуру события [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown).</span><span class="sxs-lookup"><span data-stu-id="2ed29-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="2ed29-117">Его сигнатура:</span><span class="sxs-lookup"><span data-stu-id="2ed29-117">Its signature is:</span></span>

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- <span data-ttu-id="2ed29-118">Делегат <xref:System.Windows.Forms.MouseEventHandler>, определяющий сигнатуру события [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown).</span><span class="sxs-lookup"><span data-stu-id="2ed29-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="2ed29-119">Его сигнатура:</span><span class="sxs-lookup"><span data-stu-id="2ed29-119">Its signature is:</span></span>

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

<span data-ttu-id="2ed29-120">В примере определяется обработчик событий с параметром <xref:System.EventArgs>, который используется для обработки событий `Button.KeyDown` и `Button.MouseClick`.</span><span class="sxs-lookup"><span data-stu-id="2ed29-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="2ed29-121">Это можно сделать, поскольку <xref:System.EventArgs> является базовым типом <xref:System.Windows.Forms.KeyEventArgs> и <xref:System.Windows.Forms.MouseEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="2ed29-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>

### <a name="code"></a><span data-ttu-id="2ed29-122">Код</span><span class="sxs-lookup"><span data-stu-id="2ed29-122">Code</span></span>

```vb
' Event handler that accepts a parameter of the EventArgs type.
Private Sub MultiHandler(ByVal sender As Object,
                         ByVal e As System.EventArgs)
    Label1.Text = DateTime.Now
End Sub

Private Sub Form1_Load(ByVal sender As System.Object,
    ByVal e As System.EventArgs) Handles MyBase.Load

    ' You can use a method that has an EventArgs parameter,
    ' although the event expects the KeyEventArgs parameter.
    AddHandler Button1.KeyDown, AddressOf MultiHandler

    ' You can use the same method
    ' for the event that expects the MouseEventArgs parameter.
    AddHandler Button1.MouseClick, AddressOf MultiHandler
End Sub
```

## <a name="see-also"></a><span data-ttu-id="2ed29-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2ed29-123">See also</span></span>

- [<span data-ttu-id="2ed29-124">Вариативность в делегатах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ed29-124">Variance in Delegates (Visual Basic)</span></span>](variance-in-delegates.md)
- [<span data-ttu-id="2ed29-125">Использование вариативности в универсальных методах-делегатах Func и Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ed29-125">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](using-variance-for-func-and-action-generic-delegates.md)
