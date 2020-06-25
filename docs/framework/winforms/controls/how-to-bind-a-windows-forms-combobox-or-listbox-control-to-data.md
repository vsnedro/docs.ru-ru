---
title: Привязка элемента управления ComboBox или ListBox к данным
description: Узнайте, как привязать Windows Forms ComboBox и ListBox к данным для выполнения таких задач, как просмотр данных в базе данных, ввод новых данных или изменение существующих данных.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: 0c07dc90ddc91061c5f34b5a237082cb444e89d9
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324075"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms
Можно привязывать <xref:System.Windows.Forms.ComboBox> и <xref:System.Windows.Forms.ListBox> к данным для выполнения таких задач, как просмотр данных в базе данных, ввод новых данных или изменение существующих данных.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Привязка элемента управления ComboBox или ListBox  
  
1. Задайте `DataSource` свойство для объекта источника данных. Возможные источники данных включают в себя <xref:System.Windows.Forms.BindingSource> привязку к данным, таблице данных, представлению данных, набору данных, диспетчеру представления данных, массиву или любому классу, реализующему <xref:System.Collections.IList> интерфейс. Дополнительные сведения см. [в разделе Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).  
  
2. При привязке к таблице присвойте `DisplayMember` свойству имя столбца в источнике данных.  
  
     \- или -  
  
     При привязке к <xref:System.Collections.IList> присвойте элементу вывода открытое свойство типа в списке.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    > При привязке к источнику данных, который не реализует <xref:System.ComponentModel.IBindingList> интерфейс, например <xref:System.Collections.ArrayList> , данные привязанного элемента управления не будут обновляться при обновлении источника данных. Например, при наличии поля со списком, привязанного к <xref:System.Collections.ArrayList> , и к которому добавляются данные <xref:System.Collections.ArrayList> , эти новые элементы не будут отображаться в поле со списком. Однако можно принудительно обновить поле со списком, вызвав <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> методы и в экземпляре <xref:System.Windows.Forms.BindingContext> класса, к которому привязан элемент управления.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Привязка данных Windows Forms](../windows-forms-data-binding.md)
- [Связывание данных и Windows Forms](../data-binding-and-windows-forms.md)
- [Создание списка для выбора элементов в Windows Forms](windows-forms-controls-used-to-list-options.md)
