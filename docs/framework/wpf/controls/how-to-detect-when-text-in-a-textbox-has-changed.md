---
title: Практическое руководство. Определение изменения текста в TextBox
description: Узнайте, как использовать событие TextChanged для выполнения метода при каждом изменении текста в элементе управления TextBox в Windows Presentation Foundation приложении.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1e054380a8c77d32e6bb4adbbcb032e531bbefd0
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166224"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="38e43-103">Практическое руководство. Определение изменения текста в TextBox</span><span class="sxs-lookup"><span data-stu-id="38e43-103">How to: Detect When Text in a TextBox Has Changed</span></span>

<span data-ttu-id="38e43-104">В этом примере показан один из способов использования <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> события для выполнения метода при изменении текста в <xref:System.Windows.Controls.TextBox> элементе управления.</span><span class="sxs-lookup"><span data-stu-id="38e43-104">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>

<span data-ttu-id="38e43-105">В классе кода программной части для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , содержащего <xref:System.Windows.Controls.TextBox> элемент управления, для которого необходимо отслеживать изменения, вставьте метод, который будет вызываться при каждом <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> срабатывании события.</span><span class="sxs-lookup"><span data-stu-id="38e43-105">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="38e43-106">Этот метод должен иметь сигнатуру, которая соответствует тому, что ожидается <xref:System.Windows.Controls.TextChangedEventHandler> делегатом.</span><span class="sxs-lookup"><span data-stu-id="38e43-106">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

<span data-ttu-id="38e43-107">Обработчик событий вызывается при каждом <xref:System.Windows.Controls.TextBox> изменении содержимого элемента управления либо пользователем, либо программным способом.</span><span class="sxs-lookup"><span data-stu-id="38e43-107">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="38e43-108">Это событие срабатывает при <xref:System.Windows.Controls.TextBox> создании элемента управления и его первоначальном заполнении текстом.</span><span class="sxs-lookup"><span data-stu-id="38e43-108">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

## <a name="example"></a><span data-ttu-id="38e43-109">Пример</span><span class="sxs-lookup"><span data-stu-id="38e43-109">Example</span></span>

<span data-ttu-id="38e43-110">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , определяющем <xref:System.Windows.Controls.TextBox> элемент управления, укажите <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> атрибут со значением, соответствующим имени метода обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="38e43-110">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a><span data-ttu-id="38e43-111">Пример</span><span class="sxs-lookup"><span data-stu-id="38e43-111">Example</span></span>

<span data-ttu-id="38e43-112">В классе кода программной части для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , содержащего <xref:System.Windows.Controls.TextBox> элемент управления, для которого необходимо отслеживать изменения, вставьте метод, который будет вызываться при каждом <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> срабатывании события.</span><span class="sxs-lookup"><span data-stu-id="38e43-112">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="38e43-113">Этот метод должен иметь сигнатуру, которая соответствует тому, что ожидается <xref:System.Windows.Controls.TextChangedEventHandler> делегатом.</span><span class="sxs-lookup"><span data-stu-id="38e43-113">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

<span data-ttu-id="38e43-114">Обработчик событий вызывается при каждом <xref:System.Windows.Controls.TextBox> изменении содержимого элемента управления либо пользователем, либо программным способом.</span><span class="sxs-lookup"><span data-stu-id="38e43-114">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="38e43-115">Это событие срабатывает при <xref:System.Windows.Controls.TextBox> создании элемента управления и его первоначальном заполнении текстом.</span><span class="sxs-lookup"><span data-stu-id="38e43-115">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

<span data-ttu-id="38e43-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="38e43-116">Comments</span></span>

## <a name="see-also"></a><span data-ttu-id="38e43-117">См. также</span><span class="sxs-lookup"><span data-stu-id="38e43-117">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="38e43-118">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="38e43-118">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="38e43-119">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="38e43-119">RichTextBox Overview</span></span>](richtextbox-overview.md)
