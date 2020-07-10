---
title: Общие сведения об элементе управления DataGridView
description: Узнайте, как использовать элемент управления Windows Forms DataGridView для отображения и редактирования табличных данных из различных типов источников данных.
ms.date: 03/30/2017
f1_keywords:
- DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
ms.openlocfilehash: 3e68f536853081453f6ba746d342bc016bc8ca17
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174618"
---
# <a name="datagridview-control-overview-windows-forms"></a>Общие сведения об элементе управления DataGridView (Windows Forms)
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 С помощью <xref:System.Windows.Forms.DataGridView> элемента управления можно отображать и редактировать табличные данные из различных типов источников данных.  
  
 Привязка данных к <xref:System.Windows.Forms.DataGridView> элементу управления проста и интуитивно понятна, и во многих случаях это так же просто, как установка <xref:System.Windows.Forms.DataGridView.DataSource%2A> Свойства. При привязке к источнику данных, содержащему несколько списков или таблиц, задайте <xref:System.Windows.Forms.DataGridView.DataMember%2A> для свойства строку, указывающую список или таблицу для привязки.  
  
 <xref:System.Windows.Forms.DataGridView>Элемент управления поддерживает стандартную модель привязки данных Windows Forms, поэтому она будет привязана к экземплярам классов, описанным в следующем списке:  
  
- Любой класс, реализующий <xref:System.Collections.IList> интерфейс, в том числе одномерные массивы.  
  
- Любой класс, реализующий <xref:System.ComponentModel.IListSource> интерфейс, например <xref:System.Data.DataTable> <xref:System.Data.DataSet> классы и.  
  
- Любой класс, реализующий <xref:System.ComponentModel.IBindingList> интерфейс, например <xref:System.ComponentModel.BindingList%601> класс.  
  
- Любой класс, реализующий <xref:System.ComponentModel.IBindingListView> интерфейс, например <xref:System.Windows.Forms.BindingSource> класс.  
  
 <xref:System.Windows.Forms.DataGridView>Элемент управления поддерживает привязку данных к открытым свойствам объектов, возвращаемых этими интерфейсами, или к коллекции свойств, возвращаемой <xref:System.ComponentModel.ICustomTypeDescriptor> интерфейсом, если они реализованы в возвращаемых объектах.  
  
 Как правило, выполняется привязка к <xref:System.Windows.Forms.BindingSource> компоненту и привязка <xref:System.Windows.Forms.BindingSource> компонента к другому источнику данных или заполнение его бизнес-объектами. <xref:System.Windows.Forms.BindingSource>Компонент является предпочтительным источником данных, поскольку он может выполнять привязку к различным источникам данных и может автоматически устранять множество проблем привязки данных. Дополнительные сведения см. в разделе [компонент BindingSource](bindingsource-component.md).  
  
 <xref:System.Windows.Forms.DataGridView>Элемент управления можно также использовать в *несвязанном* режиме без базового хранилища данных. Пример кода, в котором используется несвязанный <xref:System.Windows.Forms.DataGridView> элемент управления, см. в разделе [Пошаговое руководство. Создание непривязанного элемента управления Windows Forms DataGridView](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 <xref:System.Windows.Forms.DataGridView>Элемент управления обладает широкими возможностями настройки и расширяем, и предоставляет множество свойств, методов и событий для настройки внешнего вида и поведения. Если вы хотите, чтобы в приложении Windows Forms отображались табличные данные, рассмотрите возможность использования <xref:System.Windows.Forms.DataGridView> элемента управления перед другими (например, <xref:System.Windows.Forms.DataGrid> ). Если вы отображаете маленькую сетку значений, доступных только для чтения, или если вы предоставляете пользователю возможность редактировать таблицу с миллионами записей, <xref:System.Windows.Forms.DataGridView> элемент управления предоставит вам легко Программируемое, эффективное решение для памяти.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Технологическая сводка по элементам управления DataGridView](datagridview-control-technology-summary-windows-forms.md)  
 Обобщает <xref:System.Windows.Forms.DataGridView> Основные понятия элементов управления и использование связанных классов.  
  
 [Архитектура элементов управления DataGridView](datagridview-control-architecture-windows-forms.md)  
 Описывает архитектуру <xref:System.Windows.Forms.DataGridView> элемента управления, объясняя его иерархию типов и структуру наследования.  
  
 [Сценарии использования элементов управления DataGridView](datagridview-control-scenarios-windows-forms.md)  
 Описывает наиболее распространенные сценарии, в которых <xref:System.Windows.Forms.DataGridView> используются элементы управления.  
  
 [Примеры кода для элемента управления DataGridView](datagridview-control-code-directory-windows-forms.md)  
 Содержит ссылки на примеры кода в документации по различным <xref:System.Windows.Forms.DataGridView> задачам. Примеры распределены на категории по типам задач.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Типы столбцов элемента управления DataGridView в Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)  
 Описание типов столбцов в элементе управления Windows Forms, <xref:System.Windows.Forms.DataGridView> используемых для вывода сведений и предоставления пользователям возможности изменять или добавлять данные.  
  
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие заполнение элемента управления данными вручную или из внешнего источника данных.  
  
 [Настройка элементов управления DataGridView в Windows Forms](customizing-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие пользовательскую отрисовку ячеек и строк <xref:System.Windows.Forms.DataGridView>, а также создание производных ячеек, столбцов и типов строк.  
  
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Разделы, описывающие, как эффективно использовать элемент управления, чтобы избежать снижения производительности при работе с большими объемами данных.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
- [Стандартная функциональность элемента управления DataGridView в Windows Forms](default-functionality-in-the-windows-forms-datagridview-control.md)
- [Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
