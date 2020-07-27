---
title: Практическое руководство. Добавление сведений о строках в элемент управления DataGrid
description: Сведения о настройке представления данных при использовании элемента управления Windows Presentation Foundation DataGrid путем добавления раздела сведений о строке.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 8fd6b07f454681a0eed70d7a6208cfcc426dc920
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164956"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Практическое руководство. Добавление сведений о строках в элемент управления DataGrid
При использовании <xref:System.Windows.Controls.DataGrid> элемента управления можно настроить представление данных, добавив раздел сведения о строке. Добавление раздела сведений о строке позволяет сгруппировать некоторые данные в шаблон, который можно показать или свернуть. Например, можно добавить в коллекцию сведения о строках <xref:System.Windows.Controls.DataGrid> , представляющие только сводку по данным для каждой строки в <xref:System.Windows.Controls.DataGrid> , но при этом будет представлено больше полей данных, когда пользователь выбирает строку. Вы определяете шаблон для раздела сведения о строке в <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> свойстве. На следующем рисунке показан пример раздела сведений о строке.  
  
 ![Сетка DataGrid, показанная со сведениями в строке](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Шаблон сведений о строках определяется как встроенный XAML или ресурс. Оба подхода показаны в следующих процедурах. Шаблон данных, добавленный в качестве ресурса, можно использовать во всем проекте без повторного создания шаблона. Шаблон данных, добавленный как встроенный код XAML, доступен только из элемента управления, в котором он определен.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Отображение сведений о строках с помощью встроенного кода XAML  
  
1. Создайте объект <xref:System.Windows.Controls.DataGrid> , отображающий данные из источника данных.  
  
2. В элементе <xref:System.Windows.Controls.DataGrid> добавьте элемент <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3. Создайте объект <xref:System.Windows.DataTemplate> , определяющий внешний вид раздела сведения о строке.  
  
     В следующем коде XAML показано <xref:System.Windows.Controls.DataGrid> и как определить <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> встроенное. Объект <xref:System.Windows.Controls.DataGrid> отображает три значения в каждой строке и еще три значения при выборе строки.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     В следующем коде показан запрос, который используется для выбора данных, отображаемых в <xref:System.Windows.Controls.DataGrid> . В этом примере запрос выбирает данные из сущности, содержащей сведения о клиенте.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Отображение сведений о строках с помощью ресурса  
  
1. Создайте объект <xref:System.Windows.Controls.DataGrid> , отображающий данные из источника данных.  
  
2. Добавьте <xref:System.Windows.FrameworkElement.Resources%2A> элемент в корневой элемент, например <xref:System.Windows.Window> элемент управления или <xref:System.Windows.Controls.Page> элемент управления, или добавьте <xref:System.Windows.Application.Resources%2A> элемент в <xref:System.Windows.Application> класс в файле App. XAML (или Application. XAML).  
  
3. В элементе Resources создайте объект <xref:System.Windows.DataTemplate> , который определяет внешний вид раздела сведения о строке.  
  
     В следующем коде XAML показан объект, <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> определенный в <xref:System.Windows.Application> классе.  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. В <xref:System.Windows.DataTemplate> присвойте [директиве x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) значение, уникально идентифицирующее шаблон данных.  
  
5. В <xref:System.Windows.Controls.DataGrid> элементе задайте <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> для свойства ресурс, определенный на предыдущих шагах. Назначьте ресурс как статический ресурс.  
  
     В следующем коде XAML показано свойство, заданное <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> для ресурса из предыдущего примера.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Установка видимости и предотвращение горизонтальной прокрутки для сведений о строках  
  
1. При необходимости присвойте <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> свойству <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> значение.  
  
     По умолчанию устанавливается значение <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. Его можно задать для <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> отображения подробных сведений по всем строкам или <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> для скрытия сведений для всех строк.  
  
2. При необходимости задайте для <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> свойства значение, `true` чтобы предотвратить горизонтальную прокрутку раздела сведения о строке.
