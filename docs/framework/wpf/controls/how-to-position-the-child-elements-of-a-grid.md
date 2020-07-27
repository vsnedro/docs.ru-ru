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
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Практическое руководство. Размещение дочерних элементов Grid
В этом примере показано, как использовать методы get и Set, определенные в, <xref:System.Windows.Controls.Grid> для размещения дочерних элементов.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется родительский <xref:System.Windows.Controls.Grid> элемент ( `grid1` ), который содержит три столбца и три строки. Дочерний <xref:System.Windows.Shapes.Rectangle> элемент ( `rect1` ) добавляется к элементу <xref:System.Windows.Controls.Grid> в столбце в нулевом положении, нулевой позицией в строке. <xref:System.Windows.Controls.Button>элементы представляют методы, которые могут быть вызваны для изменения расположения <xref:System.Windows.Shapes.Rectangle> элемента в <xref:System.Windows.Controls.Grid> . Когда пользователь нажимает кнопку, активируется соответствующий метод.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 Следующий пример кода программной части обрабатывает методы, которые <xref:System.Windows.Controls.Primitives.ButtonBase.Click> вызывают события кнопки. В примере эти вызовы метода записываются в <xref:System.Windows.Controls.TextBlock> элементы, которые используют связанные методы get для вывода новых значений свойств в виде строк.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 Вот завершенный результат!

 ![на снимке экрана показан пользовательский интерфейс WPF с двумя столбцами, у правой стороны есть сетка 3 x 3, а слева — кнопки для перемещения цветного прямоугольника между столбцами и строками сетки.](././media/grid-methods-sample.png)
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.Grid>
- [Общие сведения о панелях](panels-overview.md)
