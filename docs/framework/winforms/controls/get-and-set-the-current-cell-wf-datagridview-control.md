---
title: Получение и задание текущей ячейки в элементе управления DataGridView
description: Узнайте, как программным способом определить, какая ячейка активна в данный момент, путем получения и установки текущей ячейки в элементе управления Windows Forms DataGridView.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 1651ca9c8fa0329f9435a70ce777bce68f15ff63
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622215"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="36a78-103">Практическое руководство. Считывание и установка значения текущей ячейки элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36a78-103">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="36a78-104">Для взаимодействия с <xref:System.Windows.Forms.DataGridView> часто требуется программно определить, какая ячейка активна в данный момент.</span><span class="sxs-lookup"><span data-stu-id="36a78-104">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="36a78-105">Также может потребоваться изменить текущую ячейку.</span><span class="sxs-lookup"><span data-stu-id="36a78-105">You may also need to change the current cell.</span></span> <span data-ttu-id="36a78-106">Эти задачи можно выполнить с помощью <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="36a78-106">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36a78-107">Нельзя задать текущую ячейку в строке или столбце, <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> для свойства которого задано значение `false` .</span><span class="sxs-lookup"><span data-stu-id="36a78-107">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="36a78-108">В зависимости от <xref:System.Windows.Forms.DataGridView> режима выбора элемента управления изменение текущей ячейки может изменить выбор.</span><span class="sxs-lookup"><span data-stu-id="36a78-108">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="36a78-109">Дополнительные сведения см. [в разделе Режимы выделения в элементе управления Windows Forms DataGridView](selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="36a78-109">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="36a78-110">Получение текущей ячейки программным способом</span><span class="sxs-lookup"><span data-stu-id="36a78-110">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="36a78-111">Используйте <xref:System.Windows.Forms.DataGridView> свойство элемента управления <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> .</span><span class="sxs-lookup"><span data-stu-id="36a78-111">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="36a78-112">Задание текущей ячейки программным способом</span><span class="sxs-lookup"><span data-stu-id="36a78-112">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="36a78-113">Задайте <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> свойство <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="36a78-113">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="36a78-114">В следующем примере кода текущей ячейке присваивается значение строка 0, столбец 1.</span><span class="sxs-lookup"><span data-stu-id="36a78-114">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="36a78-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="36a78-115">Compiling the Code</span></span>  
 <span data-ttu-id="36a78-116">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="36a78-116">This example requires:</span></span>  
  
- <span data-ttu-id="36a78-117"><xref:System.Windows.Forms.Button>элементы управления с именами `getCurrentCellButton` и `setCurrentCellButton` .</span><span class="sxs-lookup"><span data-stu-id="36a78-117"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="36a78-118">В Visual C# <xref:System.Windows.Forms.Control.Click> события для каждой кнопки необходимо прикрепить к соответствующему обработчику событий в примере кода.</span><span class="sxs-lookup"><span data-stu-id="36a78-118">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="36a78-119">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="36a78-119">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="36a78-120">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36a78-120">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a78-121">См. также</span><span class="sxs-lookup"><span data-stu-id="36a78-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="36a78-122">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36a78-122">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="36a78-123">Режимы выделения содержимого элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36a78-123">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
