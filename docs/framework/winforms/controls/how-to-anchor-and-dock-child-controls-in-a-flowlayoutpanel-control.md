---
title: Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel
description: Сведения о программной привязке и закрепления дочерних элементов управления в Windows Forms элементе управления FlowLayoutPanel.
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: b4fb3bf6d148a526a75926bd67c1f967286332bf
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174540"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="bd9fa-103">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bd9fa-103">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>

<span data-ttu-id="bd9fa-104">Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> поддерживает свойства <xref:System.Windows.Forms.Control.Anchor%2A> и <xref:System.Windows.Forms.Control.Dock%2A> в своих дочерних элементах управления.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-104">The <xref:System.Windows.Forms.FlowLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>

### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="bd9fa-105">Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bd9fa-105">To anchor and dock child controls in a FlowLayoutPanel control</span></span>

1. <span data-ttu-id="bd9fa-106">Создание элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> в форме.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-106">Create a <xref:System.Windows.Forms.FlowLayoutPanel> control on your form.</span></span>

2. <span data-ttu-id="bd9fa-107">Установите для <xref:System.Windows.Forms.Control.Width%2A> <xref:System.Windows.Forms.FlowLayoutPanel> элемента управления значение **300**и задайте для него значение <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> <xref:System.Windows.Forms.FlowDirection.TopDown> .</span><span class="sxs-lookup"><span data-stu-id="bd9fa-107">Set the <xref:System.Windows.Forms.Control.Width%2A> of the <xref:System.Windows.Forms.FlowLayoutPanel> control to **300**, and set its <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> to <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>

3. <span data-ttu-id="bd9fa-108">Создайте два элемента управления <xref:System.Windows.Forms.Button> и поместите их в элемент управления <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-108">Create two <xref:System.Windows.Forms.Button> controls, and place them in the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

4. <span data-ttu-id="bd9fa-109">Присвойте <xref:System.Windows.Forms.Control.Width%2A> первой кнопке значение **200**.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-109">Set the <xref:System.Windows.Forms.Control.Width%2A> of the first button to **200**.</span></span>

5. <span data-ttu-id="bd9fa-110">Присвойте свойству <xref:System.Windows.Forms.Control.Dock%2A> первой кнопки значение <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-110">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd9fa-111">Вторая кнопка принимает ту же ширину, что и первая кнопка.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-111">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="bd9fa-112">Она не растягивается по ширине элемента управления <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-112">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="bd9fa-113">Присвойте свойству <xref:System.Windows.Forms.Control.Dock%2A> первой кнопки значение `None`.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-113">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to `None`.</span></span> <span data-ttu-id="bd9fa-114">При этом кнопка примет исходную ширину.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-114">This causes the button to assume its original width.</span></span>

7. <span data-ttu-id="bd9fa-115">Присвойте свойству <xref:System.Windows.Forms.Control.Anchor%2A> первой кнопки значение `Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-115">Set the <xref:System.Windows.Forms.Control.Anchor%2A> property of the second button to `Left, Right`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bd9fa-116">Вторая кнопка принимает ту же ширину, что и первая кнопка.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-116">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="bd9fa-117">Она не растягивается по ширине элемента управления <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-117">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="bd9fa-118">Общее правило для привязки и закрепления в элементе управления <xref:System.Windows.Forms.FlowLayoutPanel>: в вертикальном направлении элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> вычисляет ширину предполагаемого столбца исходя из ширины самого широкого элемента управления в столбце.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-118">This is the general rule for anchoring and docking in the <xref:System.Windows.Forms.FlowLayoutPanel> control: for vertical flow directions, the <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the width of an implied column from the widest child control in the column.</span></span> <span data-ttu-id="bd9fa-119">Другие элементы управления в этом столбце со свойствами <xref:System.Windows.Forms.Control.Anchor%2A> или <xref:System.Windows.Forms.Control.Dock%2A> выравниваются или растягиваются до этого предполагаемого столбца.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-119">All other controls in this column with <xref:System.Windows.Forms.Control.Anchor%2A> or <xref:System.Windows.Forms.Control.Dock%2A> properties are aligned or stretched to fit this implied column.</span></span> <span data-ttu-id="bd9fa-120">Аналогичное поведение работает и в горизонтальном направлении.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-120">The behavior works in a similar way for horizontal flow directions.</span></span> <span data-ttu-id="bd9fa-121">Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> вычисляет высоту предполагаемой строки на основе самого высокого дочернего элемента управления в строке, и все закрепленные или привязанные дочерние элементы управления в этой строке выравниваются или их размеры устанавливаются в соответствии с предполагаемой строкой.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-121">The <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the height of an implied row from the tallest child control in the row, and all docked or anchored child controls in this row are aligned or sized to fit the implied row.</span></span>

## <a name="example"></a><span data-ttu-id="bd9fa-122">Пример</span><span class="sxs-lookup"><span data-stu-id="bd9fa-122">Example</span></span>

<span data-ttu-id="bd9fa-123">На следующем рисунке показаны четыре кнопки, привязанный и закрепленные по отношению к синей кнопке в <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-123">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="bd9fa-124"><xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> является <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-124">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span></span>

<span data-ttu-id="bd9fa-125">![Закрепление FlowLayoutPanel](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span><span class="sxs-lookup"><span data-stu-id="bd9fa-125">![FlowLayoutPanel anchoring](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span></span>

<span data-ttu-id="bd9fa-126">На следующем рисунке показаны четыре кнопки, привязанный и закрепленные по отношению к синей кнопке в <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-126">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="bd9fa-127"><xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> является <xref:System.Windows.Forms.FlowDirection.TopDown>.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-127">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>

<span data-ttu-id="bd9fa-128">![Закрепление FlowLayoutPanel](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="bd9fa-128">![FlowLayoutPanel anchoring](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span></span>

<span data-ttu-id="bd9fa-129">В следующем примере кода демонстрируются все варианты свойства <xref:System.Windows.Forms.Control.Anchor%2A> для размещения элемента управления <xref:System.Windows.Forms.Button> в элементе управления <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-129">The following code example demonstrates various <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

[!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
[!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]

## <a name="compiling-the-code"></a><span data-ttu-id="bd9fa-130">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bd9fa-130">Compiling the Code</span></span>

<span data-ttu-id="bd9fa-131">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="bd9fa-131">This example requires:</span></span>

- <span data-ttu-id="bd9fa-132">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="bd9fa-132">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd9fa-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bd9fa-133">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="bd9fa-134">Общие сведения об элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bd9fa-134">FlowLayoutPanel Control Overview</span></span>](flowlayoutpanel-control-overview.md)
