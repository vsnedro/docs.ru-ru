---
title: Размещение элементов управления
description: Узнайте, как использовать конструктор Windows Forms в Visual Studio или свойство Location для размещения элементов управления.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0aa3faade71e0f7e0a9d5e676327a80747524b8c
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904303"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="329ef-103">Как располагать элементы управления на Windows Forms</span><span class="sxs-lookup"><span data-stu-id="329ef-103">How to: Position controls on Windows Forms</span></span>

<span data-ttu-id="329ef-104">Чтобы разместить элементы управления, используйте конструктор Windows Forms в Visual Studio или укажите <xref:System.Windows.Forms.Control.Location%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="329ef-104">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="329ef-105">Размещение элемента управления в области конструктора конструктор Windows Forms</span><span class="sxs-lookup"><span data-stu-id="329ef-105">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="329ef-106">В Visual Studio перетащите элемент управления в соответствующее место с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="329ef-106">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="329ef-107">Выберите элемент управления и переместите его с помощью клавиш со СТРЕЛКАми, чтобы более точно расположить его.</span><span class="sxs-lookup"><span data-stu-id="329ef-107">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="329ef-108">Кроме того, *линии привязки* помогают точно разместить элементы управления в форме.</span><span class="sxs-lookup"><span data-stu-id="329ef-108">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="329ef-109">Дополнительные сведения см. [в разделе Пошаговое руководство. Упорядочивание элементов управления в Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="329ef-109">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="329ef-110">Размещение элемента управления с помощью окно свойств</span><span class="sxs-lookup"><span data-stu-id="329ef-110">Position a control using the Properties window</span></span>

1. <span data-ttu-id="329ef-111">В Visual Studio выберите элемент управления, который требуется разместить.</span><span class="sxs-lookup"><span data-stu-id="329ef-111">In Visual Studio, select the control you want to position.</span></span>

2. <span data-ttu-id="329ef-112">В окне **Свойства** введите значения для <xref:System.Windows.Forms.Control.Location%2A> свойства, разделенные запятыми, чтобы разместить элемент управления в контейнере.</span><span class="sxs-lookup"><span data-stu-id="329ef-112">In the **Properties** window, enter values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

   <span data-ttu-id="329ef-113">Первое число (X) — это расстояние от левой границы контейнера; второе число (Y) — это расстояние от верхней границы области контейнера, измеряемое в пикселях.</span><span class="sxs-lookup"><span data-stu-id="329ef-113">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

   > [!NOTE]
   > <span data-ttu-id="329ef-114">Можно развернуть свойство, <xref:System.Windows.Forms.Control.Location%2A> чтобы ввести значения **X** и **Y** по отдельности.</span><span class="sxs-lookup"><span data-stu-id="329ef-114">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="329ef-115">Размещение элемента управления программным способом</span><span class="sxs-lookup"><span data-stu-id="329ef-115">Position a control programmatically</span></span>

1. <span data-ttu-id="329ef-116">Присвойте <xref:System.Windows.Forms.Control.Location%2A> свойству элемента управления значение <xref:System.Drawing.Point> .</span><span class="sxs-lookup"><span data-stu-id="329ef-116">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="329ef-117">Измените координату X расположения элемента управления с помощью <xref:System.Windows.Forms.Control.Left%2A> подсвойства.</span><span class="sxs-lookup"><span data-stu-id="329ef-117">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="329ef-118">Программное увеличение расположения элемента управления</span><span class="sxs-lookup"><span data-stu-id="329ef-118">Increment a control's location programmatically</span></span>

<span data-ttu-id="329ef-119">Задайте <xref:System.Windows.Forms.Control.Left%2A> подсвойство, чтобы увеличить координату X элемента управления.</span><span class="sxs-lookup"><span data-stu-id="329ef-119">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

```vb
Button1.Left += 200
```

```csharp
button1.Left += 200;
```

```cpp
button1->Left += 200;
```

> [!NOTE]
> <span data-ttu-id="329ef-120">Используйте <xref:System.Windows.Forms.Control.Location%2A> свойство, чтобы одновременно задать координаты X и Y элемента управления.</span><span class="sxs-lookup"><span data-stu-id="329ef-120">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="329ef-121">Чтобы задать расположение по отдельности, используйте <xref:System.Windows.Forms.Control.Left%2A> подсвойство (**X**) или <xref:System.Windows.Forms.Control.Top%2A> (**Y**) элемента управления.</span><span class="sxs-lookup"><span data-stu-id="329ef-121">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="329ef-122">Не пытайтесь неявно задать координаты X и Y <xref:System.Drawing.Point> структуры, представляющей расположение кнопки, так как эта структура содержит копию координат кнопки.</span><span class="sxs-lookup"><span data-stu-id="329ef-122">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="329ef-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="329ef-123">See also</span></span>

- [<span data-ttu-id="329ef-124">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="329ef-124">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="329ef-125">Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="329ef-125">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="329ef-126">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="329ef-126">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="329ef-127">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="329ef-127">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="329ef-128">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="329ef-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="329ef-129">Элементы управления для использования в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="329ef-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="329ef-130">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="329ef-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="329ef-131">[Практическое руководство. Установка расположения форм Windows Forms на экране](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="329ef-131">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>
