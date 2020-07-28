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
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Практическое руководство. Определение изменения текста в TextBox

В этом примере показан один из способов использования <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> события для выполнения метода при изменении текста в <xref:System.Windows.Controls.TextBox> элементе управления.

В классе кода программной части для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , содержащего <xref:System.Windows.Controls.TextBox> элемент управления, для которого необходимо отслеживать изменения, вставьте метод, который будет вызываться при каждом <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> срабатывании события.  Этот метод должен иметь сигнатуру, которая соответствует тому, что ожидается <xref:System.Windows.Controls.TextChangedEventHandler> делегатом.

Обработчик событий вызывается при каждом <xref:System.Windows.Controls.TextBox> изменении содержимого элемента управления либо пользователем, либо программным способом.

> [!NOTE]
> Это событие срабатывает при <xref:System.Windows.Controls.TextBox> создании элемента управления и его первоначальном заполнении текстом.

## <a name="example"></a>Пример

В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , определяющем <xref:System.Windows.Controls.TextBox> элемент управления, укажите <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> атрибут со значением, соответствующим имени метода обработчика событий.

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a>Пример

В классе кода программной части для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , содержащего <xref:System.Windows.Controls.TextBox> элемент управления, для которого необходимо отслеживать изменения, вставьте метод, который будет вызываться при каждом <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> срабатывании события.  Этот метод должен иметь сигнатуру, которая соответствует тому, что ожидается <xref:System.Windows.Controls.TextChangedEventHandler> делегатом.

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

Обработчик событий вызывается при каждом <xref:System.Windows.Controls.TextBox> изменении содержимого элемента управления либо пользователем, либо программным способом.

> [!NOTE]
> Это событие срабатывает при <xref:System.Windows.Controls.TextBox> создании элемента управления и его первоначальном заполнении текстом.

Комментарии

## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
