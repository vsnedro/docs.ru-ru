---
title: Форматирование данных в элементе управления DataGridView
description: Узнайте, как форматировать значения ячеек с помощью свойства DefaultCellStyle элемента управления DataGridView Windows Forms и конкретных столбцов в элементе управления.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: d6105c1d1120876f854332e7a10106cc1caf6276
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622813"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6a293-103">Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a293-103">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6a293-104">Следующие процедуры демонстрируют базовое форматирование значений ячеек с помощью <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> свойства <xref:System.Windows.Forms.DataGridView> элемента управления и конкретных столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="6a293-104">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="6a293-105">Дополнительные сведения о расширенном форматировании данных см. в разделе [инструкции. Настройка форматирования данных в элементе управления Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="6a293-105">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="6a293-106">Форматирование значений денежной единицы и даты</span><span class="sxs-lookup"><span data-stu-id="6a293-106">To format currency and date values</span></span>  
  
- <span data-ttu-id="6a293-107">Задайте свойство <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="6a293-107">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="6a293-108">В следующем примере кода задается формат для конкретных столбцов с помощью <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> свойства столбцов.</span><span class="sxs-lookup"><span data-stu-id="6a293-108">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="6a293-109">Значения в `UnitPrice` столбце отображаются в текущем формате валюты, зависящем от языка и региональных параметров, с отрицательными значениями, заключенными в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="6a293-109">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="6a293-110">Значения в `ShipDate` столбце отображаются в кратком формате даты, соответствующем языку и региональным параметрам.</span><span class="sxs-lookup"><span data-stu-id="6a293-110">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="6a293-111">Дополнительные сведения о <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> значениях см. в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="6a293-111">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="6a293-112">Настройка вывода значений NULL для базы данных</span><span class="sxs-lookup"><span data-stu-id="6a293-112">To customize the display of null database values</span></span>  
  
- <span data-ttu-id="6a293-113">Задайте свойство <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="6a293-113">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="6a293-114">В следующем примере кода свойство используется <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> для вывода "без записи" во всех ячейках, содержащих значения, равные <xref:System.DBNull.Value?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6a293-114">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="6a293-115">Включение переноса слов в текстовых ячейках</span><span class="sxs-lookup"><span data-stu-id="6a293-115">To enable wordwrap in text-based cells</span></span>  
  
- <span data-ttu-id="6a293-116">Установите <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> свойство объекта в <xref:System.Windows.Forms.DataGridViewCellStyle> одно из <xref:System.Windows.Forms.DataGridViewTriState> значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="6a293-116">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="6a293-117">В следующем примере кода свойство используется <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> для задания режима переноса для всего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6a293-117">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="6a293-118">Указание выравнивания текста для ячеек DataGridView</span><span class="sxs-lookup"><span data-stu-id="6a293-118">To specify the text alignment of DataGridView cells</span></span>  
  
- <span data-ttu-id="6a293-119">Установите <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> свойство объекта в <xref:System.Windows.Forms.DataGridViewCellStyle> одно из <xref:System.Windows.Forms.DataGridViewContentAlignment> значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="6a293-119">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="6a293-120">В следующем примере кода устанавливается выравнивание для определенного столбца с помощью <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Свойства столбца.</span><span class="sxs-lookup"><span data-stu-id="6a293-120">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="6a293-121">Пример</span><span class="sxs-lookup"><span data-stu-id="6a293-121">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6a293-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6a293-122">Compiling the Code</span></span>  
 <span data-ttu-id="6a293-123">Для этих примеров требуются:</span><span class="sxs-lookup"><span data-stu-id="6a293-123">These examples require:</span></span>  
  
- <span data-ttu-id="6a293-124"><xref:System.Windows.Forms.DataGridView>Элемент управления с именем, `dataGridView1` содержащий столбец с именем, `UnitPrice` столбец с именем `ShipDate` и столбец с именем `CustomerName` .</span><span class="sxs-lookup"><span data-stu-id="6a293-124">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
- <span data-ttu-id="6a293-125">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6a293-125">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6a293-126">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="6a293-126">Robust Programming</span></span>  
 <span data-ttu-id="6a293-127">Для обеспечения максимальной масштабируемости необходимо совместно использовать <xref:System.Windows.Forms.DataGridViewCellStyle> объекты в нескольких строках, столбцах или ячейках, использующих одни и те же стили, а не задавать свойства стиля для каждого элемента отдельно.</span><span class="sxs-lookup"><span data-stu-id="6a293-127">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="6a293-128">Подробнее см. в разделе [Масштабирование элемента управления DataGridView в Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="6a293-128">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a293-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6a293-129">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="6a293-130">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a293-130">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6a293-131">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a293-131">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6a293-132">Форматирование данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a293-132">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6a293-133">Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a293-133">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6a293-134">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="6a293-134">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
