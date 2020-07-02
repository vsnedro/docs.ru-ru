---
title: Практическое руководство. Реализация проверки привязки
description: Узнайте, как использовать проверку привязки для предоставления пользователю визуальной обратной связи при вводе недопустимого значения в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 0813be9f79a83a9dae26db1dadb58b5e973339fd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617886"
---
# <a name="how-to-implement-binding-validation"></a>Практическое руководство. Реализация проверки привязки

В этом примере показано, как использовать <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> триггер типа и, чтобы предоставить визуальную обратную связь для информирования пользователя о неправильном значении на основе настраиваемого правила проверки.

## <a name="example"></a>Пример

Текстовое содержимое элемента <xref:System.Windows.Controls.TextBox> в следующем примере привязано к `Age` свойству (типа int) объекта источника привязки с именем `ods` . Привязка настроена на использование правила проверки с именем `AgeRangeRule` так, чтобы при вводе нечисловых символов или значения меньше 21 или больше 130 рядом с текстовым полем появился красный восклицательный знак и подсказка с сообщением об ошибке, когда пользователь наводит указатель мыши на текстовое поле.

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

В следующем примере показана реализация класса `AgeRangeRule` , который наследует от <xref:System.Windows.Controls.ValidationRule> и переопределяет <xref:System.Windows.Controls.ValidationRule.Validate%2A> метод. `Int32.Parse`Метод вызывается для значения, чтобы убедиться, что он не содержит недопустимых символов. <xref:System.Windows.Controls.ValidationRule.Validate%2A>Метод возвращает <xref:System.Windows.Controls.ValidationResult> , который указывает, является ли значение допустимым в зависимости от того, перехвачено исключение во время синтаксического анализа и является ли значение возраста за пределами нижней и верхней границ.

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

В следующем примере показан пользовательский параметр <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` , который создает красный восклицательный знак для уведомления пользователя об ошибке проверки. Шаблоны элементов управления используются для переопределения внешнего вида элемента управления.

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

Как показано в следующем примере, объект <xref:System.Windows.Controls.ToolTip> , отображающий сообщение об ошибке, создается с использованием стиля с именем `textBoxInError` . Если значение <xref:System.Windows.Controls.Validation.HasError%2A> равно `true` , триггер устанавливает подсказку текущего объекта <xref:System.Windows.Controls.TextBox> в первую ошибку проверки. Параметр <xref:System.Windows.Data.Binding.RelativeSource%2A> имеет значение <xref:System.Windows.Data.RelativeSourceMode.Self> , ссылающееся на текущий элемент.

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

Полный пример см. в разделе [образец проверки привязки](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).
  
Обратите внимание, что если не указать настраиваемый <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> шаблон ошибок по умолчанию, отобразится визуальный отзыв для пользователя при возникновении ошибки проверки. См. "Проверка данных" в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md). Кроме того, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет встроенное правило проверки, которое отслеживает исключения, получаемые во время обновления свойства источника привязки. Для получения дополнительной информации см. <xref:System.Windows.Controls.ExceptionValidationRule>.

## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Практические руководства](data-binding-how-to-topics.md)
