---
title: Создание слоев объектов
description: Узнайте, как выполнять слоевые объекты на Windows Forms элементах управления и дочерних формах для создания более сложных пользовательских интерфейсов.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6269b09c56963fefd500b9e1e6c9d7f51f9619cf
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174514"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="1563d-103">Как выполнять слои объектов на Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1563d-103">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="1563d-104">При создании сложного пользовательского интерфейса или работе с формой многодокументного интерфейса (MDI) часто требуется послойировать как элементы управления, так и дочерние формы, чтобы создать более сложные пользовательские интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="1563d-104">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="1563d-105">Чтобы перемещать и контролировать элементы управления и окна в контексте группы, вы управляете их *z-порядком*.</span><span class="sxs-lookup"><span data-stu-id="1563d-105">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="1563d-106">Z-порядок — это визуальное расположение элементов управления на форме вдоль оси z формы (глубина).</span><span class="sxs-lookup"><span data-stu-id="1563d-106">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="1563d-107">Окно, расположенное в верхней части z-порядка, перекрывает все остальные окна.</span><span class="sxs-lookup"><span data-stu-id="1563d-107">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="1563d-108">Все остальные окна перекрываются в нижней части z-порядка.</span><span class="sxs-lookup"><span data-stu-id="1563d-108">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="1563d-109">Для элементов управления "слой" во время разработки</span><span class="sxs-lookup"><span data-stu-id="1563d-109">To layer controls at design time</span></span>

1. <span data-ttu-id="1563d-110">В Visual Studio выберите элемент управления, который необходимо прослойировать.</span><span class="sxs-lookup"><span data-stu-id="1563d-110">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="1563d-111">В меню **Формат** выберите пункт **порядок**, а затем выберите команду **переместить на передний план** или **переместить на заднюю**.</span><span class="sxs-lookup"><span data-stu-id="1563d-111">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="1563d-112">Программное управление слоями</span><span class="sxs-lookup"><span data-stu-id="1563d-112">To layer controls programmatically</span></span>

<span data-ttu-id="1563d-113">Используйте <xref:System.Windows.Forms.Control.BringToFront%2A> методы и <xref:System.Windows.Forms.Control.SendToBack%2A> для обработки z-порядка элементов управления.</span><span class="sxs-lookup"><span data-stu-id="1563d-113">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="1563d-114">Например, если <xref:System.Windows.Forms.TextBox> элемент управления, `txtFirstName` , находится под другим элементом управления и требуется его поверх, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="1563d-114">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> <span data-ttu-id="1563d-115">Windows Forms поддерживает *Включение элементов управления*.</span><span class="sxs-lookup"><span data-stu-id="1563d-115">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="1563d-116">Включение элемента управления включает в себя размещение ряда элементов управления внутри содержащего его элемента управления, например, ряда <xref:System.Windows.Forms.RadioButton> элементов управления <xref:System.Windows.Forms.GroupBox> .</span><span class="sxs-lookup"><span data-stu-id="1563d-116">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="1563d-117">Затем можно послойировать элементы управления внутри содержащего его элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1563d-117">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="1563d-118">Перемещение поля группы также приводит к перемещению элементов управления, так как они находятся внутри него.</span><span class="sxs-lookup"><span data-stu-id="1563d-118">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="1563d-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1563d-119">See also</span></span>

- [<span data-ttu-id="1563d-120">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1563d-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="1563d-121">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1563d-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="1563d-122">Элементы управления для использования в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1563d-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="1563d-123">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1563d-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
