---
title: Различия между элементами управления DataGridView и DataGrid
description: Изучите различные различия Windows Forms между функциями элементов управления DataGridView и DataGrid, а также различиями в их архитектуре.
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: 1438182d764097ae4f8fd7df046ad72c9213da19
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174592"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Различия элементов управления DataGridView и DataGrid в Windows Forms
<xref:System.Windows.Forms.DataGridView>Элемент управления является новым элементом управления, который заменяет <xref:System.Windows.Forms.DataGrid> элемент управления. <xref:System.Windows.Forms.DataGridView>Элемент управления предоставляет множество базовых и дополнительных функций, отсутствующих в <xref:System.Windows.Forms.DataGrid> элементе управления. Кроме того, архитектура <xref:System.Windows.Forms.DataGridView> элемента управления значительно упрощает расширение и настройку, чем <xref:System.Windows.Forms.DataGrid> элемент управления.  
  
 В следующей таблице описаны некоторые основные функции, доступные в элементе управления <xref:System.Windows.Forms.DataGridView> , отсутствующие в <xref:System.Windows.Forms.DataGrid> элементе управления.  
  
|Функция элемента управления DataGridView|Описание|  
|----------------------------------|-----------------|  
|Несколько типов столбцов|<xref:System.Windows.Forms.DataGridView>Элемент управления предоставляет больше встроенных типов столбцов, чем <xref:System.Windows.Forms.DataGrid> элемент управления. Эти типы столбцов соответствуют потребностям наиболее распространенных сценариев, но их также легче расширять или заменять по сравнению с типами столбцов в <xref:System.Windows.Forms.DataGrid> элементе управления. Дополнительные сведения см. [в разделе Типы столбцов в элементе управления Windows Forms DataGridView](column-types-in-the-windows-forms-datagridview-control.md).|  
|Несколько способов отобразить данные|<xref:System.Windows.Forms.DataGrid>Элемент управления ограничен отображением данных из внешнего источника данных. <xref:System.Windows.Forms.DataGridView>Однако элемент управления может отображать несвязанные данные, хранящиеся в элементе управления, данные из привязанного источника данных, а также связанные и непривязанные данные. Можно также реализовать виртуальный режим в <xref:System.Windows.Forms.DataGridView> элементе управления для предоставления пользовательского управления данными. Дополнительные сведения см. [в разделе Режимы вывода данных в элементе управления Windows Forms DataGridView](data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Различные способы настройки представления данных|<xref:System.Windows.Forms.DataGridView>Элемент управления предоставляет множество свойств и событий, которые позволяют указать способ форматирования и отображения данных. Например, можно изменить внешний вид ячеек, строк и столбцов в зависимости от содержащихся в них данных, а также заменить данные одного типа данными эквивалентными данными другого типа. Дополнительные сведения см. [в разделе Форматирование данных в элементе управления Windows Forms DataGridView](data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Несколько параметров для изменения внешнего вида и поведения ячеек, строк, столбцов и заголовков|<xref:System.Windows.Forms.DataGridView>Элемент управления позволяет работать с отдельными компонентами сетки различными способами. Например, можно заморозить строки и столбцы, чтобы предотвратить их прокрутку. Скрытие строк, столбцов и заголовков; изменение способа корректировки размеров строк, столбцов и заголовков; изменение способа выбора пользователями. и предоставляют подсказки и контекстные меню для отдельных ячеек, строк и столбцов.|  
  
 <xref:System.Windows.Forms.DataGrid>Элемент управления сохраняется для обеспечения обратной совместимости и для специальных потребностей. Для практически всех целей следует использовать <xref:System.Windows.Forms.DataGridView> элемент управления. Единственная функция, доступная в <xref:System.Windows.Forms.DataGrid> элементе управления, которая недоступна в <xref:System.Windows.Forms.DataGridView> элементе управления, является иерархическим отображением информации из двух связанных таблиц в одном элементе управления. <xref:System.Windows.Forms.DataGridView>Для отображения сведений из двух таблиц, которые находятся в связях "основной/подробности", необходимо использовать два элемента управления.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Обновление элемента управления DataGridView  
 Если у вас есть приложения, использующие <xref:System.Windows.Forms.DataGrid> элемент управления в простом сценарии с привязкой к данным без настроек, можно просто заменить старый элемент управления новым. Оба элемента управления используют стандартную Windows Forms архитектуру привязки данных, поэтому <xref:System.Windows.Forms.DataGridView> элемент управления будет отображать привязанные данные без дополнительной настройки. Однако может возникнуть необходимость в использовании преимуществ привязок к данным, но путем привязки данных к <xref:System.Windows.Forms.BindingSource> компоненту, который затем можно привязать к <xref:System.Windows.Forms.DataGridView> элементу управления. Дополнительные сведения см. в разделе [компонент BindingSource](bindingsource-component.md).  
  
 Поскольку <xref:System.Windows.Forms.DataGridView> элемент управления имеет совершенно новую архитектуру, нет прямого пути преобразования, который позволит использовать <xref:System.Windows.Forms.DataGrid> настройки с <xref:System.Windows.Forms.DataGridView> элементом управления. <xref:System.Windows.Forms.DataGrid>Однако многие настройки не нужны для <xref:System.Windows.Forms.DataGridView> элемента управления, поскольку из-за встроенных функций, доступных в новом элементе управления. Если для <xref:System.Windows.Forms.DataGrid> элемента управления, который требуется использовать с элементом управления, созданы пользовательские типы столбцов <xref:System.Windows.Forms.DataGridView> , их потребуется реализовать снова с помощью новой архитектуры. Дополнительные сведения см. [в разделе Настройка элемента управления Windows Forms DataGridView](customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Windows.Forms.BindingSource>
- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Компонент BindingSource](bindingsource-component.md)
- [Типы столбцов элемента управления DataGridView в Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Режимы отображения данных в элементе управления DataGridView в Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Форматирование данных в элементе управления DataGridView в Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Изменение размеров управления DataGridView в Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Режимы выделения содержимого элемента управления DataGridView в Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
- [Настройка элементов управления DataGridView в Windows Forms](customizing-the-windows-forms-datagridview-control.md)
