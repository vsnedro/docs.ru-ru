---
title: Проверка ввода пользователя
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: eafbf54552566011fef9d2dbeb5e9f9fa3facabd
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646306"
---
# <a name="user-input-validation-in-windows-forms"></a>Проверка введенных пользователем данных в Windows Forms
Когда пользователи вводят данные в приложение, вы можете убедиться, что данные действительны, прежде чем приложение использует их. Вы можете потребовать, чтобы некоторые текстовые поля не были нулевой длины, чтобы поле было отформатировано как номер телефона или другой тип хорошо сформированных данных, или чтобы строка не содержала каких-либо небезопасных символов, которые могли бы быть использованы для компрометации безопасности базы данных. Windows Forms предоставляет несколько способов проверки ввода в приложении.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Проверка с помощью управления MaskedTextBox  
 Если вам необходимо требовать от пользователей вводить данные в четко определенном формате, например номер телефона или <xref:System.Windows.Forms.MaskedTextBox> номер детали, вы можете сделать это быстро и с минимальным кодом с помощью элемента управления. *Маска* представляет собой строку, состоящую из символов из маскировки языка, который определяет, какие символы могут быть введены в любой позиции в текстовом поле. Элемент управления отображает набор запросов для пользователя. Если пользователь вводит неправильный вход, например, пользователь вводит букву, когда требуется цифра, элемент управления автоматически отклоняет вход.  
  
 Язык маскировки, <xref:System.Windows.Forms.MaskedTextBox> который используется очень гибким. Это позволяет указать нужные символы, дополнительные символы, буквальные символы, такие как дефисы и скобки, валютные символы и сепараторы даты. Элемент управления также хорошо работает при привязке к источнику данных. Событие, <xref:System.Windows.Forms.Binding.Format> наряду с привязкой данных, может быть использовано <xref:System.Windows.Forms.Binding.Parse> для переформатирование входящих данных в соответствии с маской, а событие может быть использовано для переформатирование исходящих данных в соответствии со спецификациями поля данных.  
  
 Для получения дополнительной информации [см.](./controls/maskedtextbox-control-windows-forms.md)  
  
## <a name="event-driven-validation"></a>Проверка event-Driven  
 Если требуется полный программный контроль над проверкой или вам необходимо выполнить сложные проверки проверки, следует использовать события проверки, встроенные в большинство элементов управления Windows Forms. Каждый элемент управления, который принимает вход <xref:System.Windows.Forms.Control.Validating> пользователя свободной формы, имеет событие, которое будет происходить всякий раз, когда элемент управления требует проверки данных. В <xref:System.Windows.Forms.Control.Validating> методе обработки событий можно проверить ввод пользователей несколькими способами. Например, если у вас есть текстовый ящик, который должен содержать почтовый индекс, вы можете выполнить проверку следующим образом:  
  
- Если почтовый индекс должен принадлежать определенной группе почтовых индексов, можно провести сравнение строки на входе для проверки данных, введенных пользователем. Например, если почтовый индекс должен быть в наборе 10001, 10002, 10003, то для проверки данных можно использовать сравнение строки.  
  
- Если почтовый индекс должен быть в определенной форме, вы можете использовать регулярные выражения для проверки данных, введенных пользователем. Например, для проверки формы `#####` или, `#####-####`вы `^(\d{5})(-\d{4})?$`можете использовать регулярное выражение. Для проверки `A#A #A#`формы можно использовать `[A-Z]\d[A-Z] \d[A-Z]\d`регулярное выражение. Для получения дополнительной информации о регулярных выражениях [Regular Expression Examples](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md) [см.](../../standard/base-types/regular-expressions.md)  
  
- Если почтовый индекс должен быть действительным почтовым индексом Соединенных Штатов, вы можете вызвать веб-службу почтового индекса для проверки данных, введенных пользователем.  
  
 Событие <xref:System.Windows.Forms.Control.Validating> поставляется объект типа <xref:System.ComponentModel.CancelEventArgs>. Если вы установите, что данные элемента управления <xref:System.Windows.Forms.Control.Validating> недействительны, вы <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> можете `true`отменить событие, установив свойство этого объекта для Если вы не <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> установите свойство, Windows Forms предположит, что <xref:System.Windows.Forms.Control.Validated> проверка удалось для этого управления, и повысит событие.  
  
 Для примера кода, который проверяет <xref:System.Windows.Controls.TextBox>адрес <xref:System.Windows.Forms.Control.Validating>электронной почты в, см.  
  
### <a name="data-binding-and-event-driven-validation"></a>Связывание данных и проверка на основе событий  
 Проверка очень полезна, когда элементы управления связаны с источником данных, например таблицей базы данных. С помощью проверки можно убедиться, что данные элемента управления удовлетворяют формату, требуемому источником данных, и что он не содержит специальных символов, таких как кавычки и слэши спины, которые могут быть небезопасными.  
  
 При использовании связывания данных данные в элементе управления синхронизируются с источником данных во время выполнения <xref:System.Windows.Forms.Control.Validating> события. При отмене <xref:System.Windows.Forms.Control.Validating> события данные не будут синхронизированы с источником данных.  
  
> [!IMPORTANT]
> Если у вас есть пользовательская <xref:System.Windows.Forms.Control.Validating> проверка, которая происходит после события, это не повлияет на связывание данных. Например, если у вас <xref:System.Windows.Forms.Control.Validated> есть код в случае, если попытка отменить привязку данных, привязка данных все равно будет происходить. В этом случае для выполнения <xref:System.Windows.Forms.Control.Validated> проверки в случае, измените свойство **режима обновления источника данных** **(под (Databindings)**\\ **(Advanced)** с **OnValidation** на **Never,** и добавьте *control*`.DataBindings["`*\<YOURFIELD>* `"].WriteValue()` к коду проверки.  
  
### <a name="implicit-and-explicit-validation"></a>Неявная и явная проверка  
 Итак, когда данные управления проверяются? Это до вас, разработчик. Вы можете использовать неявную или явную проверку, в зависимости от потребностей приложения.  
  
#### <a name="implicit-validation"></a>Неявная проверка  
 Подход к неявной проверке проверяет данные по мере ввода пользователем. Вы можете проверить данные по мере ввода данных в элемент управления, читая клавиши при нажатии, или чаще, когда пользователь удаляет входной фокус от одного элемента управления и переходит к другому. Этот подход полезен, если вы хотите дать пользователю немедленную обратную связь о данных, как они работают.  
  
 Если вы хотите использовать неявную проверку для элемента управления, необходимо установить свойство элемента <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> управления <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange> или. <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange> При отмене <xref:System.Windows.Forms.Control.Validating> события поведение элемента управления будет определяться <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>тем значением, которое вы назначили. Если вы <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>назначены, отмена события <xref:System.Windows.Forms.Control.Validated> приведет к тому, что событие не произойдет. Вводная фокусировка будет оставаться на текущем элементе управления до тех пор, пока пользователь не изменит данные на допустимый вход. Если вы <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>назначены, <xref:System.Windows.Forms.Control.Validated> событие не произойдет при отмене события, но фокус все равно изменится на следующий элемент управления.  
  
 Назначение <xref:System.Windows.Forms.AutoValidate.Disable> <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> свойства полностью предотвращает неявную проверку. Чтобы проверить элементы управления, вам придется использовать явную проверку.  
  
#### <a name="explicit-validation"></a>Явная проверка  
 Подход явной проверки проверяет данные одновременно. Вы можете проверить данные в ответ на действия пользователя, такие как нажатие кнопки Сохранить или Следующая ссылка. При выполнении действия пользователя можно вызвать явную проверку одним из следующих способов:  
  
- Вызов <xref:System.Windows.Forms.ContainerControl.Validate%2A> для проверки последнего элемента управления, потерявшего фокус.  
  
- Вызов <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> для проверки всех элементов управления детьми в форме или контейнерном контроле.  
  
- Вызов пользовательского метода для проверки данных в элементах управления вручную.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Поведение неявной проверки по умолчанию для элементов управления формами Windows  
 Различные элементы управления Windows <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> Forms имеют различные значения по умолчанию для их свойства. В следующей таблице показаны наиболее распространенные элементы управления и их по умолчанию.  
  
|Control|Поведение проверки по умолчанию|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Недвижимость, не выставленная в Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Недвижимость, не выставленная в Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Закрытие формы и переопределение валидации  
 Когда элемент управления поддерживает фокус, поскольку данные, которые он содержит, недействительны, невозможно закрыть родительскую форму одним из обычных способов:  
  
- Нажав кнопку **"Закрыть".**  
  
- Выбрав **«Закрыть»** в меню **Системы.**  
  
- Называя <xref:System.Windows.Forms.Form.Close%2A> метод программно.  
  
 Однако в некоторых случаях может потребоваться, чтобы пользователь закрыл форму независимо от того, являются ли значения в элементах управления действительными. Можно переопределить проверку и закрыть форму, которая по-прежнему содержит недействительные данные, создав обработчик для <xref:System.Windows.Forms.Form.FormClosing> события формы. В случае, установите <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> `false`свойство для . Это заставляет форму закрываться. Дополнительные сведения и пример см. в разделе <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>.  
  
> [!NOTE]
> При принуждении к закрытию формы таким образом, любые данные в элементах управления формы, которые еще не были сохранены, теряются. Кроме того, модальные формы не проверяют содержимое элементов управления при их закрытии. Вы все еще можете использовать проверку управления для блокировки фокусировки на элементе управления, но вам не нужно беспокоиться о поведении, связанном с закрытием формы.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>
- <xref:System.Windows.Forms.FormClosingEventArgs?displayProperty=nameWithType>
- [Элемент управления MaskedTextBox](./controls/maskedtextbox-control-windows-forms.md)
- [Примеры регулярного выражения](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md)
