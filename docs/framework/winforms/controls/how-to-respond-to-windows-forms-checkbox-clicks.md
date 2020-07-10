---
title: Реагирование на нажатия флажков
description: Узнайте, как программировать приложение Windows Forms для выполнения некоторых действий в зависимости от состояния флажка.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: 58944bc421f990343b6c58484aaab3d79c8bda5e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174501"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms
Когда пользователь щелкает <xref:System.Windows.Forms.CheckBox> элемент управления Windows Forms, <xref:System.Windows.Forms.Control.Click> возникает событие. Приложение можно запрограммировать для выполнения некоторых действий в зависимости от состояния флажка.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Реагирование на нажатия кнопки CheckBox  
  
1. В <xref:System.Windows.Forms.Control.Click> обработчике событий используйте <xref:System.Windows.Forms.CheckBox.Checked%2A> свойство для определения состояния элемента управления и выполнения необходимых действий.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > Если пользователь пытается дважды щелкнуть <xref:System.Windows.Forms.CheckBox> элемент управления, каждый щелчок будет обрабатываться отдельно, то есть <xref:System.Windows.Forms.CheckBox> элемент управления не поддерживает событие двойного щелчка.  
  
    > [!NOTE]
    > Если <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> свойство имеет значение `true` (по умолчанию), то <xref:System.Windows.Forms.CheckBox> при щелчке автоматически выбирается или удаляется. В противном случае необходимо вручную задать <xref:System.Windows.Forms.CheckBox.Checked%2A> свойство при <xref:System.Windows.Forms.Control.Click> возникновении события.  
  
     Можно также использовать <xref:System.Windows.Forms.CheckBox> элемент управления для определения курса действий.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Определение курса действий при нажатии на флажок  
  
1. Используйте оператор Case для запроса значения <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойства, чтобы определить направление действия. Если <xref:System.Windows.Forms.CheckBox.ThreeState%2A> свойство имеет значение `true` , <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойство может возвращать три возможных значения, которые представляют проверяемую рамку, флажок снят, или третье неопределенное состояние, при котором окно отображается серым цветом, чтобы указать, что параметр недоступен.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > Если <xref:System.Windows.Forms.CheckBox.ThreeState%2A> свойство имеет значение `true` , <xref:System.Windows.Forms.CheckBox.Checked%2A> свойство возвращается `true` для <xref:System.Windows.Forms.CheckState.Checked> и <xref:System.Windows.Forms.CheckState.Indeterminate> .  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.CheckBox>
- [Общие сведения об элементе управления CheckBox](checkbox-control-overview-windows-forms.md)
- [Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Элемент управления CheckBox](checkbox-control-windows-forms.md)
