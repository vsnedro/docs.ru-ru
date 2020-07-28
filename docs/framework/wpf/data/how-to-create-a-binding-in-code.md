---
title: Практическое руководство. Создание привязки в коде
description: Узнайте, как создать привязку в коде приложения Windows Presentation Foundation, вызвав метод SetBinding напрямую.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: aa2a29f4c1262d8ac54641b856c297b284b23a38
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165808"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="922dc-103">Практическое руководство. Создание привязки в коде</span><span class="sxs-lookup"><span data-stu-id="922dc-103">How to: Create a Binding in Code</span></span>
<span data-ttu-id="922dc-104">В этом примере показано, как создать и задать <xref:System.Windows.Data.Binding> в коде.</span><span class="sxs-lookup"><span data-stu-id="922dc-104">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="922dc-105">Пример</span><span class="sxs-lookup"><span data-stu-id="922dc-105">Example</span></span>  
 <span data-ttu-id="922dc-106"><xref:System.Windows.FrameworkElement>Класс и <xref:System.Windows.FrameworkContentElement> класс предоставляют `SetBinding` метод.</span><span class="sxs-lookup"><span data-stu-id="922dc-106">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="922dc-107">При привязке элемента, который наследует любой из этих классов, можно вызвать <xref:System.Windows.FrameworkElement.SetBinding%2A> метод напрямую.</span><span class="sxs-lookup"><span data-stu-id="922dc-107">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="922dc-108">В следующем примере создается класс с именем, `MyData` , который содержит свойство с именем `MyDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="922dc-108">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="922dc-109">В следующем примере показано, как создать объект привязки для задания источника привязки.</span><span class="sxs-lookup"><span data-stu-id="922dc-109">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="922dc-110">В примере используется <xref:System.Windows.FrameworkElement.SetBinding%2A> для привязки <xref:System.Windows.Controls.TextBlock.Text%2A> свойства `myText` , которое является <xref:System.Windows.Controls.TextBlock> элементом управления, к `MyDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="922dc-110">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="922dc-111">Полный пример кода см. в разделе [Пример привязки только для кода](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="922dc-111">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="922dc-112">Вместо вызова <xref:System.Windows.FrameworkElement.SetBinding%2A> можно использовать <xref:System.Windows.Data.BindingOperations.SetBinding%2A> статический метод <xref:System.Windows.Data.BindingOperations> класса.</span><span class="sxs-lookup"><span data-stu-id="922dc-112">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="922dc-113">В следующем примере вызывается <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> вместо <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> для привязки к `myText` `myDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="922dc-113">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="922dc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="922dc-114">See also</span></span>

- [<span data-ttu-id="922dc-115">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="922dc-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="922dc-116">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="922dc-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
