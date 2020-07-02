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
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="d332c-103">Практическое руководство. Реализация проверки привязки</span><span class="sxs-lookup"><span data-stu-id="d332c-103">How to: Implement Binding Validation</span></span>

<span data-ttu-id="d332c-104">В этом примере показано, как использовать <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> триггер типа и, чтобы предоставить визуальную обратную связь для информирования пользователя о неправильном значении на основе настраиваемого правила проверки.</span><span class="sxs-lookup"><span data-stu-id="d332c-104">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>

## <a name="example"></a><span data-ttu-id="d332c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d332c-105">Example</span></span>

<span data-ttu-id="d332c-106">Текстовое содержимое элемента <xref:System.Windows.Controls.TextBox> в следующем примере привязано к `Age` свойству (типа int) объекта источника привязки с именем `ods` .</span><span class="sxs-lookup"><span data-stu-id="d332c-106">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="d332c-107">Привязка настроена на использование правила проверки с именем `AgeRangeRule` так, чтобы при вводе нечисловых символов или значения меньше 21 или больше 130 рядом с текстовым полем появился красный восклицательный знак и подсказка с сообщением об ошибке, когда пользователь наводит указатель мыши на текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="d332c-107">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

<span data-ttu-id="d332c-108">В следующем примере показана реализация класса `AgeRangeRule` , который наследует от <xref:System.Windows.Controls.ValidationRule> и переопределяет <xref:System.Windows.Controls.ValidationRule.Validate%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="d332c-108">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="d332c-109">`Int32.Parse`Метод вызывается для значения, чтобы убедиться, что он не содержит недопустимых символов.</span><span class="sxs-lookup"><span data-stu-id="d332c-109">The `Int32.Parse` method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="d332c-110"><xref:System.Windows.Controls.ValidationRule.Validate%2A>Метод возвращает <xref:System.Windows.Controls.ValidationResult> , который указывает, является ли значение допустимым в зависимости от того, перехвачено исключение во время синтаксического анализа и является ли значение возраста за пределами нижней и верхней границ.</span><span class="sxs-lookup"><span data-stu-id="d332c-110">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

<span data-ttu-id="d332c-111">В следующем примере показан пользовательский параметр <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` , который создает красный восклицательный знак для уведомления пользователя об ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="d332c-111">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="d332c-112">Шаблоны элементов управления используются для переопределения внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d332c-112">Control templates are used to redefine the appearance of a control.</span></span>

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

<span data-ttu-id="d332c-113">Как показано в следующем примере, объект <xref:System.Windows.Controls.ToolTip> , отображающий сообщение об ошибке, создается с использованием стиля с именем `textBoxInError` .</span><span class="sxs-lookup"><span data-stu-id="d332c-113">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="d332c-114">Если значение <xref:System.Windows.Controls.Validation.HasError%2A> равно `true` , триггер устанавливает подсказку текущего объекта <xref:System.Windows.Controls.TextBox> в первую ошибку проверки.</span><span class="sxs-lookup"><span data-stu-id="d332c-114">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="d332c-115">Параметр <xref:System.Windows.Data.Binding.RelativeSource%2A> имеет значение <xref:System.Windows.Data.RelativeSourceMode.Self> , ссылающееся на текущий элемент.</span><span class="sxs-lookup"><span data-stu-id="d332c-115">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

<span data-ttu-id="d332c-116">Полный пример см. в разделе [образец проверки привязки](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span><span class="sxs-lookup"><span data-stu-id="d332c-116">For the complete example, see [Bind Validation sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>
  
<span data-ttu-id="d332c-117">Обратите внимание, что если не указать настраиваемый <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> шаблон ошибок по умолчанию, отобразится визуальный отзыв для пользователя при возникновении ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="d332c-117">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="d332c-118">См. "Проверка данных" в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d332c-118">See "Data Validation" in [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md) for more information.</span></span> <span data-ttu-id="d332c-119">Кроме того, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет встроенное правило проверки, которое отслеживает исключения, получаемые во время обновления свойства источника привязки.</span><span class="sxs-lookup"><span data-stu-id="d332c-119">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="d332c-120">Для получения дополнительной информации см. <xref:System.Windows.Controls.ExceptionValidationRule>.</span><span class="sxs-lookup"><span data-stu-id="d332c-120">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>

## <a name="see-also"></a><span data-ttu-id="d332c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d332c-121">See also</span></span>

- [<span data-ttu-id="d332c-122">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="d332c-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="d332c-123">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="d332c-123">How-to Topics</span></span>](data-binding-how-to-topics.md)
