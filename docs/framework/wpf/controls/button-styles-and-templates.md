---
title: Стили и шаблоны элемента Button
description: Сведения о стилях и шаблонах для элемента управления "Кнопка" Windows Presentation Foundation. Измените ControlTemplate, чтобы присвоить элементу управления уникальный внешний вид.
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 11509adeef397f26eb040e6e98d0edb333b2515f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166260"
---
# <a name="button-styles-and-templates"></a>Стили и шаблоны элемента Button
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Button> элемента управления. Можно изменить значение по умолчанию, <xref:System.Windows.Controls.ControlTemplate> чтобы обеспечить уникальность внешнего вида элемента управления. Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="button-parts"></a>Части кнопки  
 <xref:System.Windows.Controls.Button>Элемент управления не имеет именованных частей.  
  
## <a name="button-states"></a>Состояния кнопок  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Button> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Нажато|CommonStates|Элемент управления нажат.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
|Допустимо|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство — `false` .|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет значение `true` , а элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>Присоединенное свойство имеет значение `true` , а элемент управления не имеет фокуса.|  
  
## <a name="button-controltemplate-example"></a>Пример ControlTemplate для кнопки  
 В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button> элемента управления.  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
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
