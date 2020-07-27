---
title: Как изменить типа курсора
description: Измените курсор указателя мыши для элемента и для приложения в Windows Presentation Foundation. Этот пример состоит из XAML и файла кода программной части.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: ce0bc290948a0e52e85f76ceb62a330b49fd87ea
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165967"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="3caec-104">Как изменить типа курсора</span><span class="sxs-lookup"><span data-stu-id="3caec-104">How to: Change the Cursor Type</span></span>
<span data-ttu-id="3caec-105">В этом примере показано, как изменить элемент <xref:System.Windows.Input.Cursor> указателя мыши для конкретного элемента и для приложения.</span><span class="sxs-lookup"><span data-stu-id="3caec-105">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="3caec-106">Этот пример состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файла и файла кода программной части.</span><span class="sxs-lookup"><span data-stu-id="3caec-106">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3caec-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3caec-107">Example</span></span>  
 <span data-ttu-id="3caec-108">Создается пользовательский интерфейс, который состоит из, <xref:System.Windows.Controls.ComboBox> чтобы выбрать нужную <xref:System.Windows.Input.Cursor> пару <xref:System.Windows.Controls.RadioButton> объектов, чтобы определить, применяется ли изменение курсора только к одному элементу или к целому приложению, а <xref:System.Windows.Controls.Border> какой элемент является элементом, к которому применяется новый курсор.</span><span class="sxs-lookup"><span data-stu-id="3caec-108">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="3caec-109">В следующем коде создается <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> обработчик событий, который вызывается при изменении типа курсора в <xref:System.Windows.Controls.ComboBox> .</span><span class="sxs-lookup"><span data-stu-id="3caec-109">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="3caec-110">Оператор Switch фильтрует по имени курсора и задает <xref:System.Windows.FrameworkElement.Cursor%2A> свойство для с <xref:System.Windows.Controls.Border> именем *дисплайареа*.</span><span class="sxs-lookup"><span data-stu-id="3caec-110">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="3caec-111">Если для изменения курсора задано значение "целое приложение", <xref:System.Windows.Input.Mouse.OverrideCursor%2A> свойству элемента управления задается свойство <xref:System.Windows.FrameworkElement.Cursor%2A> <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="3caec-111">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="3caec-112">Это заставляет курсор измениться для всего приложения.</span><span class="sxs-lookup"><span data-stu-id="3caec-112">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="3caec-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3caec-113">See also</span></span>

- [<span data-ttu-id="3caec-114">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="3caec-114">Input Overview</span></span>](input-overview.md)
