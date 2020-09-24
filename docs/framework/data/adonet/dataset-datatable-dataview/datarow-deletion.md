---
title: Удаление DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 2092d7319a398bbdeaef764d677818f78ddf9de9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153356"
---
# <a name="datarow-deletion"></a>Удаление DataRow

Существует два метода, которые можно использовать для удаления <xref:System.Data.DataRow> объекта из <xref:System.Data.DataTable> объекта: метод **Remove** <xref:System.Data.DataRowCollection> объекта и <xref:System.Data.DataRow.Delete%2A> метод объекта **DataRow** . В то время как <xref:System.Data.DataRowCollection.Remove%2A> метод удаляет **DataRow** из **датаровколлектион**, <xref:System.Data.DataRow.Delete%2A> метод помечает только строку для удаления. Фактическое удаление происходит, когда приложение вызывает метод **AcceptChanges** . Использование метода <xref:System.Data.DataRow.Delete%2A> позволяет программно проверять, какие строки помечены для удаления, перед их фактическим удалением. Когда строка отмечена для удаления, ее свойство <xref:System.Data.DataRow.RowState%2A> имеет значение <xref:System.Data.DataRow.Delete%2A>.  
  
 Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не должны вызываться в цикле foreach во время итерации по объекту <xref:System.Data.DataRowCollection>. Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не изменяет состояние коллекции.  
  
 При использовании <xref:System.Data.DataSet> **таблицы** данных или в сочетании с **DataAdapter** и реляционным источником данных используйте метод **Delete** объекта **DataRow** для удаления строки. Метод **Delete** помечает строку как **удаленную** в **наборе данных** или **DataTable** , но не удаляет ее. Вместо этого, когда **DataAdapter** обнаруживает строку, помеченную как **Удаленная**, она выполняет метод **DeleteCommand** для удаления строки в источнике данных. Затем строку можно удалить без возможности восстановления с помощью метода **AcceptChanges** . При использовании метода **Remove** для удаления строки строка удаляется полностью из таблицы, но **DataAdapter** не удаляет строку в источнике данных.  
  
 Метод **Remove** объекта **датаровколлектион** принимает **DataRow** в качестве аргумента и удаляет его из коллекции, как показано в следующем примере.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 В следующем примере показано, как вызвать метод **Delete** для **DataRow** , чтобы изменить его свойство **RowState** на **deleted**.  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Если строка помечена для удаления и вызывается метод **AcceptChanges** объекта **DataTable** , то строка удаляется из **DataTable**. В отличие от этого, при **RejectChanges**вызове RejectChanges **RowState** строки восстанавливается до того, как она была помечена как **Удаленная**.  
  
> [!NOTE]
> Если **добавляется** **RowState** объекта **DataRow** , то есть он был только что добавлен в таблицу, а затем помечается как **Удаленный**, он удаляется из таблицы.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Управление данными в таблице данных](manipulating-data-in-a-datatable.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
