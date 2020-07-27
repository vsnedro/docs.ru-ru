---
title: Стили и шаблоны элемента TextBox
description: Сведения о стилях и шаблонах для элемента управления TextBox Windows Presentation Foundation. Измените ControlTemplate, чтобы присвоить элементу управления уникальный внешний вид.
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 0e15fd40f5590ee46da49cc6c0d5fb30e051f7e4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164736"
---
# <a name="textbox-styles-and-templates"></a>Стили и шаблоны элемента TextBox
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.TextBox> элемента управления. Можно изменить значение по умолчанию, <xref:System.Windows.Controls.ControlTemplate> чтобы обеспечить уникальность внешнего вида элемента управления. Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="textbox-parts"></a>Части текстового поля  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.TextBox> элемента управления.  
  
|Часть|Тип|Описание|  
|-|-|-|  
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement> . Текст <xref:System.Windows.Controls.TextBox> отображается в этом элементе.|  
  
## <a name="textbox-states"></a>Состояния текстового поля  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.TextBox> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|----------------------|---------------------------|-----------------|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|ReadOnly|CommonStates|Пользователь не может изменить текст в <xref:System.Windows.Controls.TextBox> .|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|Допустимо|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство — `false` .|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет `true` фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство `true` имеет элемент управления, не имеющий фокуса.|  
  
## <a name="textbox-controltemplate-example"></a>Пример ControlTemplate для TextBox  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.TextBox> элемента управления.  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
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
