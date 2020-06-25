---
title: Скрыть столбцы в элементе управления DataGridView
description: Узнайте, как программно скрыть столбцы в элементе управления Windows Forms DataGridView, установив для свойства DataGridViewColumn. Visible значение false.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], hiding columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
ms.assetid: 3f94143a-2ef0-49a5-a22a-b2e6f9289642
ms.openlocfilehash: 46d7faea76098406b8e0a91d22922bf9ca391e28
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325906"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f2533-103">Практическое руководство. Скрытие столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2533-103">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f2533-104">Иногда требуется показать только некоторые из столбцов, доступных в элементе управления <xref:System.Windows.Forms.DataGridView> Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f2533-104">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f2533-105">Например, руководителям может потребоваться показать столбец с заработной платой сотрудников, в то время как от других пользователей его нужно скрыть.</span><span class="sxs-lookup"><span data-stu-id="f2533-105">For example, you might want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="f2533-106">Или может возникнуть необходимость привязать элемент управления к источнику данных, содержащему много столбцов, только часть из которых нужно показать.</span><span class="sxs-lookup"><span data-stu-id="f2533-106">Alternately, you might want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="f2533-107">В этом случае столбцы, которые не следует показывать, обычно не скрываются, а удаляются.</span><span class="sxs-lookup"><span data-stu-id="f2533-107">In this case, you will typically remove the columns you are not interested in displaying rather than hide them.</span></span>  
  
 <span data-ttu-id="f2533-108">В элементе управления <xref:System.Windows.Forms.DataGridView> значение свойства <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> столбца определяет, будет ли этот столбец показан.</span><span class="sxs-lookup"><span data-stu-id="f2533-108">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property value of a column determines whether that column is displayed.</span></span>  
  
 <span data-ttu-id="f2533-109">Эта задача поддерживается в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f2533-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="f2533-110">См. также [руководство. скрытие столбцов в элементе управления Windows Forms DataGridView с помощью конструктора](hide-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="f2533-110">Also see [How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer](hide-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-hide-a-column-programmatically"></a><span data-ttu-id="f2533-111">Как скрыть столбец программным образом</span><span class="sxs-lookup"><span data-stu-id="f2533-111">To hide a column programmatically</span></span>  
  
- <span data-ttu-id="f2533-112">Задайте для свойства <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f2533-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> property to `false`.</span></span> <span data-ttu-id="f2533-113">Чтобы скрыть столбец `CustomerID`, создаваемый автоматически во время привязки к данным, поместите приведенный ниже пример кода в обработчик событий <xref:System.Windows.Forms.DataGridView.DataBindingComplete>.</span><span class="sxs-lookup"><span data-stu-id="f2533-113">To hide a `CustomerID` column that is automatically generated during data binding, place the following code example in a <xref:System.Windows.Forms.DataGridView.DataBindingComplete> event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#063)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#063)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f2533-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f2533-114">Compiling the Code</span></span>  
 <span data-ttu-id="f2533-115">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f2533-115">This example requires:</span></span>  
  
- <span data-ttu-id="f2533-116">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `CustomerID`;</span><span class="sxs-lookup"><span data-stu-id="f2533-116">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `CustomerID`.</span></span>  
  
- <span data-ttu-id="f2533-117">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f2533-117">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2533-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f2533-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f2533-119">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2533-119">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="f2533-120">Практическое руководство. Удаление автоматически сгенерированных столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2533-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
- [<span data-ttu-id="f2533-121">Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2533-121">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)
