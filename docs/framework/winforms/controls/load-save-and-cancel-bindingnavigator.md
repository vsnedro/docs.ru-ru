---
title: Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator
description: Узнайте, как добавлять кнопки загрузки, сохранения и отмены в Windows Forms элемент управления BindingNavigator.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: d4db91b8cfaf2df253d0c4cf5d8a66e9157d4986
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173423"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms

<xref:System.Windows.Forms.BindingNavigator>Элемент управления — это специализированный <xref:System.Windows.Forms.ToolStrip> элемент управления, предназначенный для навигации по элементам управления формы, привязанным к данным, и манипулирования ими.

Поскольку это <xref:System.Windows.Forms.ToolStrip> элемент управления, <xref:System.Windows.Forms.BindingNavigator> компонент можно легко изменить, включив в него дополнительные или альтернативные команды для пользователя.

В следующей процедуре <xref:System.Windows.Forms.TextBox> элемент управления привязан к данным, а <xref:System.Windows.Forms.ToolStrip> элемент управления, добавляемый в форму, изменяется для включения кнопок загрузки, сохранения и отмены.

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Добавление кнопок загрузки, сохранения и отмены в компонент BindingNavigator

1. В Visual Studio добавьте в <xref:System.Windows.Forms.TextBox> форму элемент управления.

2. Привяжите его к <xref:System.Windows.Forms.BindingSource> , который привязан к источнику данных. В этом примере <xref:System.Windows.Forms.BindingSource> Привязка привязана к базе данных.

3. После создания набора данных и адаптера таблицы перетащите <xref:System.Windows.Forms.BindingNavigator> элемент управления в форму.

4. Присвойте <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> свойству элемента управления значение в <xref:System.Windows.Forms.BindingSource> форме, привязанной к элементам управления.

5. Выберите элемент управления <xref:System.Windows.Forms.BindingNavigator>.

6. Щелкните глиф действия конструктора ( ![ маленькая черная стрелка ](./media/designer-actions-glyph.gif) ), чтобы появилась диалоговое окно **Задачи BindingNavigator** , и выберите **изменить элементы**.

     Откроется **Редактор коллекции элементов** .

7. В **редакторе коллекции элементов**выполните следующие действия.

    1. Добавьте <xref:System.Windows.Forms.ToolStripSeparator> и три <xref:System.Windows.Forms.ToolStripButton> элемента, выбрав соответствующий тип <xref:System.Windows.Forms.ToolStripItem> и нажав кнопку **Добавить** .

    2. Задайте <xref:System.Windows.Forms.ToolStripItem.Name%2A> для свойств кнопок значение **лоадбуттон**, **савебуттон**и **CancelButton**соответственно.

    3. Задайте <xref:System.Windows.Forms.ToolStripItem.Text%2A> для свойства кнопки значение **Загрузка**, **Сохранение**и **Отмена**.

    4. Присвойте <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> свойству каждой кнопки значение **Text**. Кроме того, можно задать для этого свойства значение **Image** или **имажеандтекст**и задать отображение изображения в <xref:System.Windows.Forms.ToolStripItem.Image%2A> свойстве.

    5. Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно. Кнопки добавляются в <xref:System.Windows.Forms.ToolStrip> .

8. Щелкните форму правой кнопкой мыши и выберите команду **Просмотреть код**.

9. В редакторе кода найдите строку кода, которая загружает данные в адаптер таблицы. Этот код был создан при настройке привязки данных на шаге 2. Код должен выглядеть следующим образом: `TableAdapterName.Fill(DataSetName.TableName)` . Скорее всего, оно будет содержаться в <xref:System.Windows.Forms.Form.Load> событии формы.

10. Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> события **Load** <xref:System.Windows.Forms.ToolStripButton> ранее созданной нагрузки и переместите в нее этот код загрузки данных.

     Теперь ваш код должен выглядеть следующим образом:

    ```vb
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click
        TableAdapterName.Fill(DataSetName.TableName)
    End Sub
    ```

    ```csharp
    private void LoadButton_Click(System.Object sender,
        System.EventArgs e)
    {
        TableAdapterName.Fill(DataSetName.TableName);
    }
    ```

11. Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> события **Save** <xref:System.Windows.Forms.ToolStripButton> ранее созданного сохранения и напишите код для обновления данных в таблице, к которой привязан элемент управления.

    ```vb
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click
        TableAdapterName.Update(DataSetName.TableName)
    End Sub
    ```

    ```csharp
    private void SaveButton_Click(System.Object sender,
        System.EventArgs e)
    {
        TableAdapterName.Update(DataSetName.TableName);
    }
    ```

    > [!NOTE]
    > В некоторых случаях в <xref:System.Windows.Forms.BindingNavigator> компоненте уже есть кнопка **сохранить** , но конструктор Windows Forms не был создан код. В этом случае можно поместить приведенный выше код в <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий для этой кнопки, а не создавать совершенно новую кнопку на <xref:System.Windows.Forms.ToolStrip> . Однако кнопка по умолчанию отключена, поэтому необходимо задать для свойства кнопки значение, чтобы <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> `true` функция кнопки была правильной.

12. Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> события **отмены** , <xref:System.Windows.Forms.ToolStripButton> созданного ранее, и напишите код, чтобы отменить все изменения, внесенные в отображаемую запись данных.

    ```vb
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click
        BindingSourceName.CancelEdit()
    End Sub
    ```

    ```csharp
    private void CancelButton_Click(System.Object sender, System.EventArgs e)
    {
        BindingSourceName.CancelEdit();
    }
    ```

    > [!NOTE]
    > Метод ограничивается <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> строкой данных. Сохраните все изменения, внесенные при просмотре отдельной записи, прежде чем переходить к следующей записи.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [BindingNavigator — элемент управления](bindingnavigator-control-windows-forms.md)
- [Общие сведения о компоненте BindingSource](bindingsource-component-overview.md)
