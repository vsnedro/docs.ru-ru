---
title: Практическое руководство. Управление обновлением источника из поля TextBox
description: Управление временем обновлений источника привязки с помощью свойства UpdateSourceTrigger в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: 8f6eb5beb0d14a951f6e6cf6eb81e130f5a3e194
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622787"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Практическое руководство. Управление обновлением источника из поля TextBox
В этом разделе описывается использование <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойства для управления временем обновления источника привязки. В разделе используется <xref:System.Windows.Controls.TextBox> элемент управления в качестве примера.

## <a name="example"></a>Пример
 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>Свойство имеет значение по умолчанию <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> . Это означает, что если приложение имеет <xref:System.Windows.Controls.TextBox> свойство со свойством, привязанным к данным, то текст, введенный в <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> , не <xref:System.Windows.Controls.TextBox> обновляет источник до тех пор, пока не будет <xref:System.Windows.Controls.TextBox> утрачен фокус (например, при щелчке мышью вне <xref:System.Windows.Controls.TextBox> ).

 Если вы хотите, чтобы источник обновлялся по мере ввода, задайте <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> для привязки значение <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> . В следующем примере выделенные строки кода показывают, что `Text` свойства <xref:System.Windows.Controls.TextBox> и и <xref:System.Windows.Controls.TextBlock> привязаны к одному и тому же свойству источника. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>Свойству <xref:System.Windows.Controls.TextBox> привязки присвоено значение <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> .

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 В результате объект <xref:System.Windows.Controls.TextBlock> отображает тот же текст (так как источник изменяется) при вводе пользователем текста в <xref:System.Windows.Controls.TextBox> , как показано на следующем снимке экрана примера:

 ![Снимок экрана, на котором показана простая привязка данных.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 Если у вас есть диалоговое окно или пользовательская форма, и вы хотите отложить обновления источника до тех пор, пока пользователь не закончит редактирование полей и не нажмет кнопку "ОК", можно задать <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> для привязок значение <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> , как показано в следующем примере:

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 Если <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значение равно <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> , исходное значение изменяется только тогда, когда приложение вызывает <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> метод. В следующем примере показано, как вызвать метод <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> для `itemNameTextBox` :

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> Эту же методику можно использовать для свойств других элементов управления, но помните, что большинство других свойств имеют значение по умолчанию <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> . Дополнительные сведения см <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> . на странице свойств.

> [!NOTE]
> <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>Свойство работает с обновлениями источника и, следовательно, относится только <xref:System.Windows.Data.BindingMode.TwoWay> к <xref:System.Windows.Data.BindingMode.OneWayToSource> привязкам или. <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> Чтобы привязки и работали, исходный объект должен предоставлять уведомления об изменении свойств. Можно изучить примеры, приведенные в этом разделе, для получения дополнительной информации. Кроме того, см. раздел [Реализация уведомления об изменении свойства](how-to-implement-property-change-notification.md).

## <a name="see-also"></a>См. также

- [Практические руководства](data-binding-how-to-topics.md)
