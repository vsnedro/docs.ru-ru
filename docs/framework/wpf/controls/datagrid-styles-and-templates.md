---
title: Стили и шаблоны элемента DataGrid
description: Сведения о стилях и шаблонах для элемента управления Windows Presentation Foundation DataGrid. Измените ControlTemplate, чтобы присвоить элементу управления уникальный внешний вид.
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], DataGrid
- ControlTemplate [WPF], DataGrid
- DataGrid [WPF], styles and templates
- templates [WPF], DataGrid
- styles [WPF], DataGrid
- parts [WPF], DataGrid
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
ms.openlocfilehash: dd526ec64d5077dad58f31c004f47e63c57ec9de
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168332"
---
# <a name="datagrid-styles-and-templates"></a>Стили и шаблоны элемента DataGrid
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.DataGrid> элемента управления. Можно изменить значение по умолчанию, <xref:System.Windows.Controls.ControlTemplate> чтобы обеспечить уникальность внешнего вида элемента управления. Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="datagrid-parts"></a>Части DataGrid  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.DataGrid> элемента управления.  
  
|Часть|Тип|Описание|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|Строка, содержащая заголовки столбцов.|  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для в <xref:System.Windows.Controls.DataGrid> шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.DataGrid> ; <xref:System.Windows.Controls.ScrollViewer> включает прокрутку в элементе управления).  Если объект не <xref:System.Windows.Controls.ItemsPresenter> является прямым дочерним элементом объекта <xref:System.Windows.Controls.ScrollViewer> , необходимо присвоить ему <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter` .  
  
 Шаблон по умолчанию для <xref:System.Windows.Controls.DataGrid> содержит <xref:System.Windows.Controls.ScrollViewer> элемент управления. Дополнительные сведения о частях, определенных в <xref:System.Windows.Controls.ScrollViewer> , см. в разделе [ScrollViewer Styles and Templates](scrollviewer-styles-and-templates.md).  
  
## <a name="datagrid-states"></a>Состояния DataGrid  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.DataGrid> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Допустимо|ValidationStates|Элемент управления является допустимым.|  
  
## <a name="datagridcell-parts"></a>Датагридцелл части  
 <xref:System.Windows.Controls.DataGridCell>Элемент не имеет именованных частей.  
  
## <a name="datagridcell-states"></a>Состояния Датагридцелл  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.DataGridCell> элемента.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши располагается над ячейкой.|  
|Focused|FocusStates|Ячейка имеет фокус.|  
|Без фокуса ввода|FocusStates|Ячейка не имеет фокуса|  
|Текущие|куррентстатес|Ячейка является текущей ячейкой.|  
|Регулярно|куррентстатес|Ячейка не является текущей ячейкой.|  
|Отображение|интерактионстатес|Ячейка находится в режиме просмотра.|  
|Редактирование|интерактионстатес|Ячейка находится в режиме редактирования.|  
|Выбрано|SelectionStates|Ячейка выделена.|  
|Unselected|SelectionStates|Ячейка не выбрана.|  
|InvalidFocused|ValidationStates|Ячейка является недопустимой и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Ячейка не является допустимой и не имеет фокуса.|  
|Допустимо|ValidationStates|Ячейка является допустимой.|  
  
## <a name="datagridrow-parts"></a>Датагридров части  
 <xref:System.Windows.Controls.DataGridRow>Элемент не имеет именованных частей.  
  
## <a name="datagridrow-states"></a>Состояния Датагридров  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.DataGridRow> элемента.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши располагается над строкой.|  
|MouseOver_Editing|CommonStates|Указатель мыши располагается над строкой, а строка находится в режиме редактирования.|  
|MouseOver_Selected|CommonStates|Указатель мыши располагается над строкой и выбирается строка.|  
|MouseOver_Unfocused_Editing|CommonStates|Указатель мыши располагается над строкой, строка находится в режиме редактирования и не имеет фокуса.|  
|MouseOver_Unfocused_Selected|CommonStates|Указатель мыши располагается над строкой, строка выбирается и не имеет фокуса.|  
|Normal_AlternatingRow|CommonStates|Строка является альтернативной строкой.|  
|Normal_Editing|CommonStates|Строка находится в режиме редактирования.|  
|Normal_Selected|CommonStates|Строка выбрана.|  
|Unfocused_Editing|CommonStates|Строка находится в режиме редактирования и не имеет фокуса.|  
|Unfocused_Selected|CommonStates|Строка выбрана и не имеет фокуса.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Допустимо|ValidationStates|Элемент управления является допустимым.|  
  
## <a name="datagridrowheader-parts"></a>Датагридровхеадер части  
 В следующей таблице перечислены именованные части для <xref:System.Windows.Controls.Primitives.DataGridRowHeader> элемента.  
  
|Часть|Тип|Описание|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка строки сверху.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка строки снизу.|  
  
## <a name="datagridrowheader-states"></a>Состояния Датагридровхеадер  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.DataGridRowHeader> элемента.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши располагается над строкой.|  
|MouseOver_CurrentRow|CommonStates|Указатель мыши располагается над строкой, а строка — текущей строкой.|  
|MouseOver_CurrentRow_Selected|CommonStates|Указатель мыши располагается над строкой, а строка является текущей и выбранной.|  
|MouseOver_EditingRow|CommonStates|Указатель мыши располагается над строкой, а строка находится в режиме редактирования.|  
|MouseOver_Selected|CommonStates|Указатель мыши располагается над строкой и выбирается строка.|  
|MouseOver_Unfocused_CurrentRow_Selected|CommonStates|Указатель мыши располагается над строкой, строка является текущей и выбрана и не имеет фокуса.|  
|MouseOver_Unfocused_EditingRow|CommonStates|Указатель мыши располагается над строкой, строка находится в режиме редактирования и не имеет фокуса.|  
|MouseOver_Unfocused_Selected|CommonStates|Указатель мыши располагается над строкой, строка выбирается и не имеет фокуса.|  
|Normal_CurrentRow|CommonStates|Строка является текущей строкой.|  
|Normal_CurrentRow_Selected|CommonStates|Строка является текущей строкой и выбрана.|  
|Normal_EditingRow|CommonStates|Строка находится в режиме редактирования.|  
|Normal_Selected|CommonStates|Строка выбрана.|  
|Unfocused_CurrentRow_Selected|CommonStates|Строка является текущей строкой, выбрана и не имеет фокуса.|  
|Unfocused_EditingRow|CommonStates|Строка находится в режиме редактирования и не имеет фокуса.|  
|Unfocused_Selected|CommonStates|Строка выбрана и не имеет фокуса.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Допустимо|ValidationStates|Элемент управления является допустимым.|  
  
## <a name="datagridcolumnheaderspresenter-parts"></a>Датагридколумнхеадерспресентер части  
 В следующей таблице перечислены именованные части для <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> элемента.  
  
|Часть|Тип|Описание|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|Заполнитель для заголовков столбцов.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>Состояния Датагридколумнхеадерспресентер  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> элемента.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|InvalidFocused|ValidationStates|Ячейка является недопустимой и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Ячейка не является допустимой и не имеет фокуса.|  
|Допустимо|ValidationStates|Ячейка является допустимой.|  
  
## <a name="datagridcolumnheader-parts"></a>DataGridColumnHeader части  
 В следующей таблице перечислены именованные части для <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> элемента.  
  
|Часть|Тип|Описание|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка столбца слева.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка столбца справа.|  
  
## <a name="datagridcolumnheader-states"></a>Состояния DataGridColumnHeader  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> элемента.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Нажато|CommonStates|Элемент управления нажат.|  
|сортасцендинг|сортстатес|Столбец сортируется в возрастающем порядке.|  
|сортдесцендинг|сортстатес|Столбец сортируется в порядке убывания.|  
|Без сортировки|сортстатес|Столбец не отсортирован.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Допустимо|ValidationStates|Элемент управления является допустимым.|  
  
## <a name="datagrid-controltemplate-example"></a>Пример ControlTemplate для элемента управления DataGrid  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.DataGrid> элемента управления и связанных с ним типов.  
  
 [!code-xaml[ControlTemplateExamples#DataGrid](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 В предыдущем примере используется один или несколько из следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стили и шаблоны элемента Control](control-styles-and-templates.md)
- [Настройка элементов управления](control-customization.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Создание шаблона элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md)
