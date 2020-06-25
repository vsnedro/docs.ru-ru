---
title: Добавление элементов управления
description: Научитесь нарисовать элемент управления в форме Windows Forms. Элемент управления — это компонент в форме, с помощью которого можно отображать сведения или принимать вводимые пользователем данные.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: d9ab0d78fa0153cce20fb17d22f6e9e781229ece
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325880"
---
# <a name="how-to-add-controls-to-windows-forms"></a>Практическое руководство. Добавление элементов управления в формы Windows Forms.

Большинство форм разрабатываются путем добавления элементов управления на поверхность формы для определения пользовательского интерфейса. *Элемент управления* — это компонент в форме, используемый для вывода информации или ввода данных пользователем. Дополнительные сведения об элементах управления см. в разделе [элементы управления Windows Forms](index.md).

## <a name="to-draw-a-control-on-a-form"></a>Рисование элемента управления в форме

1. Откройте форму. Дополнительные сведения см. в разделе [инструкции. отображение Windows Forms в конструкторе](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. В **области элементов**щелкните элемент управления, который необходимо добавить в форму.

3. В форме щелкните место, где должен располагаться левый верхний угол элемента управления, и перетащите его в то место, где должен располагаться правый нижний угол элемента управления.

    Элемент управления добавляется в форму с указанными расположением и размером.

    > [!NOTE]
    > Для каждого элемента управления определен размер по умолчанию. Можно добавить элемент управления в форму в размер элемента управления по умолчанию, перетащив его из **области элементов** в форму.

## <a name="to-drag-a-control-to-a-form"></a>Перетаскивание элемента управления в форму

1. Откройте форму. Дополнительные сведения см. в разделе [инструкции. отображение Windows Forms в конструкторе](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. На **панели элементов**щелкните нужный элемент управления и перетащите его в форму.

    Элемент управления добавляется в форму в указанном расположении в его размер по умолчанию.

    > [!NOTE]
    > Можно дважды щелкнуть элемент управления на **панели элементов** , чтобы добавить его в левый верхний угол формы в его размер по умолчанию.

    Кроме того, можно динамически добавлять элементы управления в форму во время выполнения. В следующем примере кода <xref:System.Windows.Forms.TextBox> элемент управления будет добавлен в форму при <xref:System.Windows.Forms.Button> щелчке элемента управления.

    > [!NOTE]
    > Следующая процедура требует наличия формы с элементом управления **Button** , `Button1` уже размещенным в ней.

## <a name="to-add-a-control-to-a-form-programmatically"></a>Добавление элемента управления в форму программным способом

1. В методе, обрабатывающем событие кнопки `Click` в классе формы, вставьте код, аналогичный приведенному ниже, чтобы добавить ссылку на переменную элемента управления, задать элемент управления `Location` и добавить элемент управления.

    ```vb
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
       Dim MyText As New TextBox()
       MyText.Location = New Point(25, 25)
       Me.Controls.Add(MyText)
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
       TextBox myText = new TextBox();
       myText.Location = new Point(25,25);
       this.Controls.Add (myText);
    }
    ```

    ```cpp
    private:
      System::Void button1_Click(System::Object ^  sender,
        System::EventArgs ^  e)
      {
        TextBox ^ myText = gcnew TextBox();
        myText->Location = Point(25,25);
        this->Controls->Add(myText);
      }
    ```

    > [!NOTE]
    > Можно также добавить код для инициализации других свойств элемента управления.

    > [!IMPORTANT]
    > Вы можете предоставить локальному компьютеру угрозу безопасности через сеть, обратившись к вредоносной программе `UserControl` . Это будет проблемой только в случае, если злоумышленник создает вредоносный пользовательский элемент управления, а затем добавляет его в проект по ошибке.

## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Практическое руководство. Изменение размера элементов управления в формах Windows Forms](how-to-resize-controls-on-windows-forms.md)
- [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Элементы управления для использования в формах Windows Forms](controls-to-use-on-windows-forms.md)
