---
title: DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid column types [WPF]
- DataGrid scenarios [WPF]
- DataGrid control [WPF]
- controls [WPF], DataGrid
- DataGrid [WPF], common tasks for
- DataGrid [WPF], customizing the appearance of
- DataGrid columns [WPF], using
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
ms.openlocfilehash: cdf4bfff8182b62d55f56b823c7ff129de4f9f1c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646117"
---
# <a name="datagrid"></a>DataGrid
Элемент <xref:System.Windows.Controls.DataGrid> управления позволяет отображать и отсеивать данные из различных источников, например из базы данных S'L, запроса LIN' или любого другого связываемого источника данных. Дополнительные сведения см. в разделе [Общие сведения об источниках привязки](../data/binding-sources-overview.md).  
  
 Столбцы могут отображать текст, элементы управления, такие как <xref:System.Windows.Controls.ComboBox>содержимое WPF, например изображения, кнопки или любое содержимое, содержащееся в шаблоне. Можно использовать <xref:System.Windows.Controls.DataGridTemplateColumn> для отображения данных, определенных в шаблоне. В следующей таблице перечислены типы столбцов, которые предоставляются по умолчанию.  
  
|Тип генерируемой колонки|Тип данных|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid>могут быть настроены по внешнему виду, например, шрифту, цвету и размеру. <xref:System.Windows.Controls.DataGrid>поддерживает все функциональные возможности укладки и шаблонов других элементов управления WPF. <xref:System.Windows.Controls.DataGrid>также включает в себя поведение по умолчанию и настраиваемое поведение для редактирования, сортировки и проверки.  
  
 В следующей таблице перечислены <xref:System.Windows.Controls.DataGrid> некоторые общие задачи и способы их выполнения. Просматривая связанный API, вы можете найти дополнительную информацию и пример кода.  
  
|Сценарий|Подход|  
|--------------|--------------|  
|Чередование фоновых цветов|Установите <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> свойство до 2 или более, <xref:System.Windows.Controls.DataGrid.RowBackground%2A> а <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> затем назначить <xref:System.Windows.Media.Brush> и свойства.|  
|Определение поведения выбора ячеек и строк|Укажите свойства <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> и <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.|  
|Настройка внешнего внешнего вида заголовков, ячеек и строк|Применить новый <xref:System.Windows.Style> <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>к <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A> <xref:System.Windows.Controls.DataGrid.CellStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowStyle%2A> , или свойства.|  
|Установка параметров размеров|Установите <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MinWidth%2A> , или свойства. Для получения дополнительной информации смотрите [параметры размера в управлении DataGrid](sizing-options-in-the-datagrid-control.md).|  
|Доступ к выбранным элементам|Проверьте <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> свойство, чтобы получить <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> выбранные ячейки и свойство, чтобы получить выбранные строки. Для получения дополнительной информации см. <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Настройка взаимодействия конечных пользователей|Установите <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A> <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A> <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> , и свойства.|  
|Отмена или изменение автоматически генерируемых столбцов|Обймите <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> событие.|  
|Заморозить столбец|Установите <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> свойство до 1 и переместите столбец в положение левой, установив свойство <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> до 0.|  
|Используйте данные XML в качестве источника данных|<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Привязать к <xref:System.Windows.Controls.DataGrid> запросу XPath запрос, представляющий коллекцию элементов. Создайте каждый <xref:System.Windows.Controls.DataGrid>столбец в . Связать каждый столбец, установив XPath на привязку к запросу, который получает свойство на источнике элемента. Пример см. в разделе <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Пошаговое руководство. Отображение данных из базы данных SQL Server в элементе управления DataGrid](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Описывает, как настроить новый проект WPF, добавить элемент рамочной системы <xref:System.Windows.Controls.DataGrid>entity, установить источник и отобразить данные в разделе .|  
|[Практическое руководство. Добавление сведений о строках в элемент управления DataGrid](how-to-add-row-details-to-a-datagrid-control.md)|Описывает, как создать детали <xref:System.Windows.Controls.DataGrid>строки для .|  
|[Практическое руководство. Реализация проверки с помощью элемента управления DataGrid](how-to-implement-validation-with-the-datagrid-control.md)|Описывает, как проверить <xref:System.Windows.Controls.DataGrid> значения в ячейках и строках, а также отображать отзывы о проверке.|  
|[Поведение мыши и клавиатуры по умолчанию в элементе управления DataGrid](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Описывает, как взаимодействовать с управлением <xref:System.Windows.Controls.DataGrid> с помощью клавиатуры и мыши.|  
|[Практическое руководство. Группировка, сортировка и фильтрация данных в элементе управления DataGrid](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Описывает, как просматривать <xref:System.Windows.Controls.DataGrid> данные по-разному, группируя, сортируя и фильтруя данные.|  
|[Параметры изменения размеров элемента управления DataGrid](sizing-options-in-the-datagrid-control.md)|Описывает, как контролировать абсолютный <xref:System.Windows.Controls.DataGrid>и автоматический размер в .|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.DataGrid>
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения о шаблонах данных](../data/data-templating-overview.md)
- [Элементы управления](index.md)
- [Модель содержимого WPF](wpf-content-model.md)
