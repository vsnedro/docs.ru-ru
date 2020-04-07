---
title: Стили и шаблоны элемента ToggleButton
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805911"
---
# <a name="togglebutton-styles-and-templates"></a>Стили и шаблоны элемента ToggleButton

Эта тема описывает стили и <xref:System.Windows.Controls.Primitives.ToggleButton> шаблоны для управления. Вы можете изменить <xref:System.Windows.Controls.ControlTemplate> значение по умолчанию, чтобы придать элементу управления уникальный внешний вид. Для получения дополнительной информации [см.](../../../desktop-wpf/themes/how-to-create-apply-template.md)

## <a name="togglebutton-parts"></a>Части тглкиКнопка

Элемент <xref:System.Windows.Controls.Primitives.ToggleButton> управления не имеет никаких названных частей.

## <a name="togglebutton-states"></a>Состояния Тглгкстона

В следующей таблице перечислены <xref:System.Windows.Controls.Primitives.ToggleButton> визуальные состояния для управления.

|Имя VisualState|Имя VisualStateGroup|Описание|
|-|-|-|
|Нормальный|CommonStates|Состояние по умолчанию.|
|MouseOver|CommonStates|Указатель мыши расположен над элементом управления.|
|Нажато|CommonStates|Элемент управления нажат.|
|Выключено|CommonStates|Элемент управления отключен.|
|Focused|FocusStates|Элемент управления имеет фокус.|
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|
|Флажок установлен|Контрольные штаты|Параметр <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> равен `true`.|
|Флажок снят.|Контрольные штаты|Параметр <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> равен `false`.|
|Неопределенное|Контрольные штаты|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> равно `true`, а <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> равно `null`.|
|Допустимо|ValidationStates|Элемент управления <xref:System.Windows.Controls.Validation> использует класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `false`прилагаемое свойство находится под контролем.|
|InvalidFocused|ValidationStates|Прилагаемое <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `true` свойство и элемент управления имеет фокус.|
|InvalidUnfocused|ValidationStates|Прилагаемое <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `true` свойство и элемент управления не имеет фокуса.|

> [!NOTE]
> Если неопределенное визуальное состояние не существует в шаблоне управления, то неконтролируемое визуальное состояние будет использоваться в качестве визуального состояния по умолчанию.

## <a name="togglebutton-controltemplate-example"></a>Пример управления тглочками

В следующем примере показано, <xref:System.Windows.Controls.Primitives.ToggleButton> как определить <xref:System.Windows.Controls.ControlTemplate> элемент управления.

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

В предыдущем примере используется один или несколько из следующих ресурсов.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Стили и шаблоны элемента Control](control-styles-and-templates.md)
- [Настройка элементов управления](control-customization.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Создание шаблона для управления](../../../desktop-wpf/themes/how-to-create-apply-template.md)
