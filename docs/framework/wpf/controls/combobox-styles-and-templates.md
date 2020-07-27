---
title: Стили и шаблоны элемента ComboBox
description: Сведения о стилях и шаблонах для элемента управления ComboBox Windows Presentation Foundation. Измените ControlTemplate, чтобы присвоить элементу управления уникальный внешний вид.
ms.date: 03/30/2017
helpviewer_keywords:
- ComboBox [WPF], styles and templates
- states [WPF], ComboBox
- ControlTemplate [WPF], ComboBox
- styles [WPF], ComboBox
- templates [WPF], ComboBox
- parts [WPF], ComboBox
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
ms.openlocfilehash: 5e929bafeaf849b4b5682a17ca51cb0aab963613
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165916"
---
# <a name="combobox-styles-and-templates"></a>Стили и шаблоны элемента ComboBox
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ComboBox> элемента управления. Можно изменить значение по умолчанию, <xref:System.Windows.Controls.ControlTemplate> чтобы обеспечить уникальность внешнего вида элемента управления. Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="combobox-parts"></a>Части поля со списком  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.ComboBox> элемента управления.  
  
|Часть|Тип|Описание|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Содержит текст <xref:System.Windows.Controls.ComboBox> .|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Раскрывающийся список, содержащий элементы в поле со списком.|  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для в <xref:System.Windows.Controls.ComboBox> шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.ComboBox> ; <xref:System.Windows.Controls.ScrollViewer> включает прокрутку в элементе управления).  Если объект не <xref:System.Windows.Controls.ItemsPresenter> является прямым дочерним элементом объекта <xref:System.Windows.Controls.ScrollViewer> , необходимо присвоить ему <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter` .  
  
## <a name="combobox-states"></a>Состояния ComboBox  
 В следующей таблице перечислены состояния для <xref:System.Windows.Controls.ComboBox> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|MouseOver|CommonStates|Указатель мыши находится над <xref:System.Windows.Controls.ComboBox> элементом управления.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|фокуседдропдовн|FocusStates|Раскрывающийся список для <xref:System.Windows.Controls.ComboBox> имеет фокус.|  
|Допустимо|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство — `false` .|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет значение `true` , а элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет значение `true` , а элемент управления не имеет фокуса.|  
|Editable|едитстатес|Значение свойства <xref:System.Windows.Controls.ComboBox.IsEditable%2A> — `true`.|  
|Недоступными|едитстатес|Значение свойства <xref:System.Windows.Controls.ComboBox.IsEditable%2A> — `false`.|  
  
## <a name="comboboxitem-parts"></a>Комбобокситем части  
 <xref:System.Windows.Controls.ComboBoxItem>Элемент управления не имеет именованных частей.  
  
## <a name="comboboxitem-states"></a>Состояния Комбобокситем  
 В следующей таблице перечислены состояния для <xref:System.Windows.Controls.ComboBoxItem> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|MouseOver|CommonStates|Указатель мыши находится над <xref:System.Windows.Controls.ComboBoxItem> элементом управления.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|Выбрано|SelectionStates|Элемент выбран в данный момент.|  
|Unselected|SelectionStates|Элемент не выбран.|  
|SelectedUnfocused|SelectionStates|Элемент выбран, но не имеет фокуса.|  
|Допустимо|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство — `false` .|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет значение `true` , а элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет значение `true` , а элемент управления не имеет фокуса.|  
  
## <a name="combobox-controltemplate-example"></a>Пример поля ControlTemplate ComboBox  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ComboBox> элемента управления и связанных с ним типов.  
  
 [!code-xaml[ControlTemplateExamples#ComboBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
 В предыдущем примере используется один или несколько из следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стили и шаблоны элемента Control](control-styles-and-templates.md)
- [Настройка элементов управления](control-customization.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Создание шаблона элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md)
