---
title: Практическое руководство. Реализация проверки с помощью элемента управления DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: 38b4c9cd7679f0d8da9b18fb5bd6bb729d33ed54
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646091"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Практическое руководство. Реализация проверки с помощью элемента управления DataGrid
Элемент <xref:System.Windows.Controls.DataGrid> управления позволяет выполнять проверку как на уровне ячейки, так и на уровне строки. При проверке уровня ячейки вы проверяете отдельные свойства связанного объекта данных, когда пользователь обновляет значение. При проверке уровня строки проверяется целые объекты данных при фиксации пользователем изменений в строку. Вы также можете предоставить индивидуальную визуальную обратную связь <xref:System.Windows.Controls.DataGrid> для ошибок проверки, или использовать визуальную обратную связь по умолчанию, которую обеспечивает элемент управления.  
  
 Следующие процедуры описывают, как <xref:System.Windows.Controls.DataGrid> применять правила проверки к привязки и настроить визуальную обратную связь.  
  
### <a name="to-validate-individual-cell-values"></a>Для проверки значений отдельных ячеек  
  
- Укажите одно или несколько правил проверки на привязке, используемой с столбецом. Это похоже на проверку данных в простых элементах управления, как описано в [обзоре связывания данных.](../../../desktop-wpf/data/data-binding-overview.md)  
  
     В следующем примере <xref:System.Windows.Controls.DataGrid> показан элемент управления с четырьмя столбцов, связанными с различными свойствами бизнес-объекта. Три столбца указывают <xref:System.Windows.Controls.ExceptionValidationRule> свойство. <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> `true`  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Когда пользователь вводит недействительное значение (например, нецелый в столбце идентификатора курса), вокруг ячейки появляется красная граница. Вы можете изменить эту обратную связь проверки по умолчанию, описанную в следующей процедуре.  
  
### <a name="to-customize-cell-validation-feedback"></a>Настройка обратной связи с проверкой ячейки  
  
- Установите <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> свойство столбца в стиль, подходящий для управления редактированием столбца. Поскольку элементы управления редактированием создаются <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> во время выполнения, вы не можете использовать прикрепленное свойство, как это было бы с простыми элементами управления.  
  
     Следующий пример обновляет предыдущий пример, добавляя стиль ошибки, разделяемый тремя столбцами, с правилами проверки. Когда пользователь вводит недействительное значение, стиль изменяет цвет фона ячейки и добавляет ToolTip. Обратите внимание на использование триггера, чтобы определить, есть ли ошибка проверки. Это необходимо, поскольку в настоящее время нет выделенного шаблона ошибок для ячеек.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Можно реализовать более обширную настройку, заменив используемую <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> столбец.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Для проверки нескольких значений в одной строке  
  
1. Реализация <xref:System.Windows.Controls.ValidationRule> подкласса, проверяющий несколько свойств связанного объекта данных. При <xref:System.Windows.Controls.ValidationRule.Validate%2A> реализации метода `value` отбросьте значение параметра в <xref:System.Windows.Data.BindingGroup> экземпляр. Затем можно получить доступ к <xref:System.Windows.Data.BindingGroup.Items%2A> объекту данных через свойство.  
  
     Следующий пример демонстрирует этот процесс, `StartDate` чтобы проверить, является ли значение свойства для `Course` объекта раньше, чем его `EndDate` значение свойства.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Добавьте правило проверки <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> в коллекцию. Свойство <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> обеспечивает прямой <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> доступ <xref:System.Windows.Data.BindingGroup> к свойству экземпляра, который группирует все привязки, используемые элементом управления.  
  
     Следующий пример <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> приводит свойство в XAML. Свойство <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> настроено <xref:System.Windows.Controls.ValidationStep.UpdatedValue> на то, чтобы проверка происходила только после обновления связанного объекта данных.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Когда пользователь указывает дату окончания, которая раньше даты начала, красный восклицательный знак (!) появляется в заголовке строки. Вы можете изменить эту обратную связь проверки по умолчанию, описанную в следующей процедуре.  
  
### <a name="to-customize-row-validation-feedback"></a>Настройка обратной связи с проверкой строки  
  
- Задайте свойство <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>. Это свойство позволяет настроить отзывы о <xref:System.Windows.Controls.DataGrid> проверке строки для отдельных элементов управления. Вы также можете повлиять на несколько элементов управления, используя неявный стиль строки для установки <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> свойства.  
  
     Следующий пример заменяет обратную связь проверки строки по умолчанию более заметным индикатором. Когда пользователь вводит недействительное значение, в заголовке строки появляется красный круг с белым восклицательным знаком. Это происходит как для ошибок проверки строки и ячейки. Связанное сообщение об ошибке отображается в ToolTip.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Пример  
 Следующий пример обеспечивает полную демонстрацию для проверки ячейки и строки. Класс `Course` предоставляет объект выборочных данных, который реализуется для поддержки <xref:System.ComponentModel.IEditableObject> транзакций. Контроль <xref:System.Windows.Controls.DataGrid> взаимодействует <xref:System.ComponentModel.IEditableObject> с, чтобы позволить пользователям вернуть изменения, нажав ESC.  
  
> [!NOTE]
> Если вы используете Visual Basic, в первой строке MainWindow.xaml, замените `x:Class="DataGridValidation.MainWindow"` `x:Class="MainWindow"`на .  
  
 Чтобы проверить проверку, попробуйте следующее:  
  
- В столбце ИДЕНтификатор курса введите значение, не входявное.  
  
- В столбце «Дата окончания» введите дату, которая раньше даты начала.  
  
- Удалите значение в идентификаторе курса, дате начала или дате окончания.  
  
- Чтобы отменить недействительное значение ячейки, поместите курсор обратно в ячейку и нажмите клавишу ESC.  
  
- Чтобы отменить изменения для всей строки, когда текущая ячейка находится в режиме изменения, нажмите ключ ESC дважды.  
  
- При возникновении ошибки проверки переместите указатель мыши по индикатору в заголовке строки, чтобы увидеть связанное сообщение об ошибке.  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [Связывание данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Реализация обязательной проверки](../data/how-to-implement-binding-validation.md)
- [Реализация логики проверки на пользовательских объектах](../data/how-to-implement-validation-logic-on-custom-objects.md)
