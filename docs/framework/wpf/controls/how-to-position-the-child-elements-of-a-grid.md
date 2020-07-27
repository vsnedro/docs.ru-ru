---
title: Практическое руководство. Размещение дочерних элементов Grid
description: Узнайте, как использовать методы get и Set, определенные в Windows Presentation Foundation сетке для размещения дочерних элементов.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 926d223097dd21dd0292c9523903b4be8aba8ba9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167401"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="c0ebb-103">Практическое руководство. Размещение дочерних элементов Grid</span><span class="sxs-lookup"><span data-stu-id="c0ebb-103">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="c0ebb-104">В этом примере показано, как использовать методы get и Set, определенные в, <xref:System.Windows.Controls.Grid> для размещения дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="c0ebb-104">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0ebb-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c0ebb-105">Example</span></span>  
 <span data-ttu-id="c0ebb-106">В следующем примере определяется родительский <xref:System.Windows.Controls.Grid> элемент ( `grid1` ), который содержит три столбца и три строки.</span><span class="sxs-lookup"><span data-stu-id="c0ebb-106">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="c0ebb-107">Дочерний <xref:System.Windows.Shapes.Rectangle> элемент ( `rect1` ) добавляется к элементу <xref:System.Windows.Controls.Grid> в столбце в нулевом положении, нулевой позицией в строке.</span><span class="sxs-lookup"><span data-stu-id="c0ebb-107">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="c0ebb-108"><xref:System.Windows.Controls.Button>элементы представляют методы, которые могут быть вызваны для изменения расположения <xref:System.Windows.Shapes.Rectangle> элемента в <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="c0ebb-108"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="c0ebb-109">Когда пользователь нажимает кнопку, активируется соответствующий метод.</span><span class="sxs-lookup"><span data-stu-id="c0ebb-109">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="c0ebb-110">Следующий пример кода программной части обрабатывает методы, которые <xref:System.Windows.Controls.Primitives.ButtonBase.Click> вызывают события кнопки.</span><span class="sxs-lookup"><span data-stu-id="c0ebb-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="c0ebb-111">В примере эти вызовы метода записываются в <xref:System.Windows.Controls.TextBlock> элементы, которые используют связанные методы get для вывода новых значений свойств в виде строк.</span><span class="sxs-lookup"><span data-stu-id="c0ebb-111">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="c0ebb-112">Вот завершенный результат!</span><span class="sxs-lookup"><span data-stu-id="c0ebb-112">Here is the finished result!</span></span>

 ![на снимке экрана показан пользовательский интерфейс WPF с двумя столбцами, у правой стороны есть сетка 3 x 3, а слева — кнопки для перемещения цветного прямоугольника между столбцами и строками сетки.](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="c0ebb-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c0ebb-114">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="c0ebb-115">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="c0ebb-115">Panels Overview</span></span>](panels-overview.md)
