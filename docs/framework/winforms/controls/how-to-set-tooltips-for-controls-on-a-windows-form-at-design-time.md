---
title: Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки
description: Сведения о настройке подсказок для элементов управления программным способом или в конструктор Windows Forms в Visual Studio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 144ba5b6bffb4a538e345f7b2df4a453fc6fd63d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618029"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="64a48-103">Как задать подсказки для элементов управления в форме Windows во время разработки</span><span class="sxs-lookup"><span data-stu-id="64a48-103">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="64a48-104">Строку можно задать <xref:System.Windows.Forms.ToolTip> в коде или в конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="64a48-104">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="64a48-105">Дополнительные сведения о <xref:System.Windows.Forms.ToolTip> компоненте см. в разделе [Общие сведения о компоненте ToolTip](tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="64a48-105">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="64a48-106">Программное задание подсказки</span><span class="sxs-lookup"><span data-stu-id="64a48-106">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="64a48-107">Добавьте элемент управления, который будет отображать подсказку.</span><span class="sxs-lookup"><span data-stu-id="64a48-107">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="64a48-108">Используйте <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> метод <xref:System.Windows.Forms.ToolTip> компонента.</span><span class="sxs-lookup"><span data-stu-id="64a48-108">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="64a48-109">Задание подсказки в конструкторе</span><span class="sxs-lookup"><span data-stu-id="64a48-109">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="64a48-110">В Visual Studio добавьте компонент в <xref:System.Windows.Forms.ToolTip> форму.</span><span class="sxs-lookup"><span data-stu-id="64a48-110">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="64a48-111">Выберите элемент управления, который будет отображать подсказку, или добавьте его в форму.</span><span class="sxs-lookup"><span data-stu-id="64a48-111">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="64a48-112">В окне " **Свойства** " установите **подсказку для значения ToolTip1** в соответствующую строку текста.</span><span class="sxs-lookup"><span data-stu-id="64a48-112">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="64a48-113">Удаление подсказки программными средствами</span><span class="sxs-lookup"><span data-stu-id="64a48-113">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="64a48-114">Используйте <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> метод <xref:System.Windows.Forms.ToolTip> компонента.</span><span class="sxs-lookup"><span data-stu-id="64a48-114">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="64a48-115">Удаление подсказки в конструкторе</span><span class="sxs-lookup"><span data-stu-id="64a48-115">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="64a48-116">В Visual Studio выберите элемент управления, отображающий подсказку.</span><span class="sxs-lookup"><span data-stu-id="64a48-116">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="64a48-117">В окне **Свойства** удалите текст из **подсказки в ToolTip1**.</span><span class="sxs-lookup"><span data-stu-id="64a48-117">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="64a48-118">См. также</span><span class="sxs-lookup"><span data-stu-id="64a48-118">See also</span></span>

- [<span data-ttu-id="64a48-119">Общие сведения об элементе управления ToolTip</span><span class="sxs-lookup"><span data-stu-id="64a48-119">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="64a48-120">Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64a48-120">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="64a48-121">Компонент ToolTip</span><span class="sxs-lookup"><span data-stu-id="64a48-121">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
