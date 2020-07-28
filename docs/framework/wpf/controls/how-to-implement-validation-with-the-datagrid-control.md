---
title: Практическое руководство. Реализация проверки с помощью элемента управления DataGrid
description: Узнайте, как элемент управления Windows Presentation Foundation DataGrid может выполнять проверку как на уровне ячеек, так и в строках и оставлять отзывы об ошибках проверки.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: a6fe3693f94c3f554e96bc167b572cf854a1a34a
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167609"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Практическое руководство. Реализация проверки с помощью элемента управления DataGrid
<xref:System.Windows.Controls.DataGrid>Элемент управления позволяет выполнять проверку на уровне ячеек и строк. При проверке на уровне ячейки вы проверяете отдельные свойства привязанного объекта данных, когда пользователь обновляет значение. При проверке на уровне строк выполняется проверка всех объектов данных, когда пользователь фиксирует изменения в строке. Можно также предоставить настраиваемые визуальные Отзывы об ошибках проверки или использовать визуальный отзыв по умолчанию, <xref:System.Windows.Controls.DataGrid> предоставляемый элементом управления.  
  
 В следующих процедурах описывается применение правил проверки к <xref:System.Windows.Controls.DataGrid> привязкам и настройка визуальной обратной связи.  
  
### <a name="to-validate-individual-cell-values"></a>Проверка значений отдельных ячеек  
  
- Укажите одно или несколько правил проверки для привязки, используемой со столбцом. Это похоже на проверку данных в простых элементах управления, как описано в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).  
  
     В следующем примере показан <xref:System.Windows.Controls.DataGrid> элемент управления с четырьмя столбцами, привязанными к различным свойствам бизнес-объекта. Три столбца указывают, <xref:System.Windows.Controls.ExceptionValidationRule> присвоив <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> свойству значение `true` .  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Когда пользователь вводит недопустимое значение (например, не целое число в столбце Course ID), вокруг ячейки появляется красная граница. Можно изменить этот отзыв по проверке по умолчанию, как описано в следующей процедуре.  
  
### <a name="to-customize-cell-validation-feedback"></a>Настройка обратной связи по проверке ячейки  
  
- Задайте <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> для свойства столбца стиль, соответствующий элементу управления для редактирования столбца. Поскольку элементы управления для редактирования создаются во время выполнения, нельзя использовать <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> присоединенное свойство, как и для простых элементов управления.  
  
     Следующий пример обновляет предыдущий пример, добавляя стиль ошибки, совместно используемый тремя столбцами с правилами проверки. Когда пользователь вводит недопустимое значение, стиль изменяет цвет фона ячейки и добавляет подсказку. Обратите внимание на использование триггера для определения наличия ошибки проверки. Это необходимо, так как в настоящее время нет выделенного шаблона ошибок для ячеек.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Можно реализовать более обширную настройку, заменив значение, <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> используемое столбцом.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Проверка нескольких значений в одной строке  
  
1. Реализуйте <xref:System.Windows.Controls.ValidationRule> подкласс, который проверяет несколько свойств привязанного объекта данных. В <xref:System.Windows.Controls.ValidationRule.Validate%2A> реализации метода приведите `value` значение параметра к <xref:System.Windows.Data.BindingGroup> экземпляру. Затем можно получить доступ к объекту данных с помощью <xref:System.Windows.Data.BindingGroup.Items%2A> Свойства.  
  
     В следующем примере показан этот процесс для проверки того, `StartDate` является ли значение свойства `Course` объекта более ранним, чем `EndDate` значение его свойства.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Добавьте правило проверки в <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> коллекцию. <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>Свойство предоставляет прямой доступ к <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> свойству <xref:System.Windows.Data.BindingGroup> экземпляра, который группирует все привязки, используемые элементом управления.  
  
     В следующем примере задается <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> свойство в XAML. <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>Свойство имеет значение, <xref:System.Windows.Controls.ValidationStep.UpdatedValue> поэтому проверка выполняется только после обновления привязанного объекта данных.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Когда пользователь указывает дату окончания, предшествующую дате начала, в заголовке строки появляется красный восклицательный знак (!). Можно изменить этот отзыв по проверке по умолчанию, как описано в следующей процедуре.  
  
### <a name="to-customize-row-validation-feedback"></a>Настройка обратной связи по проверке строк  
  
- Задайте свойство <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>. Это свойство позволяет настроить отзыв о проверке строк для отдельных <xref:System.Windows.Controls.DataGrid> элементов управления. Можно также повлиять на несколько элементов управления, используя неявный стиль строк для задания <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> Свойства.  
  
     В следующем примере отменяется обратная связь по проверке строк по умолчанию с более видимым индикатором. Когда пользователь вводит недопустимое значение, в заголовке строки появляется красный кружок с белым восклицательным знаком. Это происходит как для ошибок проверки строк, так и для ячеек. Связанное сообщение об ошибке отображается в подсказке.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Пример  
 В следующем примере приведена полная демонстрация проверки ячеек и строк. `Course`Класс предоставляет образец объекта данных, который реализует <xref:System.ComponentModel.IEditableObject> для поддержки транзакций. <xref:System.Windows.Controls.DataGrid>Элемент управления взаимодействует с, позволяя <xref:System.ComponentModel.IEditableObject> пользователям отменить изменения, нажав клавишу ESC.  
  
> [!NOTE]
> При использовании Visual Basic в первой строке файла MainWindow. XAML замените на `x:Class="DataGridValidation.MainWindow"` `x:Class="MainWindow"` .  
  
 Чтобы проверить проверку, попробуйте выполнить следующие действия.  
  
- В столбце Course ID (идентификатор курса) введите значение, отличное от целого.  
  
- В столбце Дата окончания введите дату, предшествующую дате начала.  
  
- Удалите значение в поле идентификатор курса, Дата начала или Дата окончания.  
  
- Чтобы отменить недопустимое значение ячейки, установите курсор обратно в ячейку и нажмите клавишу ESC.  
  
- Чтобы отменить изменения для всей строки, если текущая ячейка находится в режиме редактирования, нажмите клавишу ESC дважды.  
  
- При возникновении ошибки проверки наведите указатель мыши на индикатор в заголовке строки, чтобы просмотреть соответствующее сообщение об ошибке.  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [Привязка данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Реализация проверки привязки](../data/how-to-implement-binding-validation.md)
- [Реализация логики проверки для пользовательских объектов](../data/how-to-implement-validation-logic-on-custom-objects.md)
