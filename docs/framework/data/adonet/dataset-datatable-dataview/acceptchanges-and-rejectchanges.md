---
description: 'Дополнительные сведения о: AcceptChanges и RejectChanges'
title: AcceptChanges и RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: e21952063bf27f4f969669eb76b964fc7537b59a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725263"
---
# <a name="acceptchanges-and-rejectchanges"></a>AcceptChanges и RejectChanges

После проверки точности изменений, внесенных в данные в <xref:System.Data.DataTable> , можно принять изменения с помощью <xref:System.Data.DataRow.AcceptChanges%2A> метода <xref:System.Data.DataRow> , <xref:System.Data.DataTable> или <xref:System.Data.DataSet> , который установит **текущие** значения строк в качестве **исходных** значений, и установит для свойства **RowState** значение **без изменений**. При принятии или отклонении изменений удаляется любая **роверрор** информация, а свойству **HasErrors** присваивается **значение false**. Принятие или отклонение изменений также может затрагивать обновление данных в источнике данных. Дополнительные сведения см. в разделе [Обновление источников данных с помощью DataAdapter](../updating-data-sources-with-dataadapters.md).  
  
 Если в **DataTable** существуют ограничения внешнего ключа, изменения, принятые или Отклоненные с помощью **AcceptChanges** и **RejectChanges** , распространяются на дочерние строки **DataRow** в соответствии с объектом **ForeignKeyConstraint. акцептрежектруле**. Дополнительные сведения см. в разделе [ограничения DataTable](datatable-constraints.md).  
  
 В следующем примере происходит проверка на наличие строк с ошибками, по возможности устраняются ошибки и отклоняются строки, в которых ошибка не может быть устранена. Обратите внимание, что для разрешенных ошибок значение **роверрор** сбрасывается в пустую строку, в результате чего свойство **HasErrors** устанавливается в значение **false**. Если все строки с ошибками были разрешены или отклонены, вызывается метод **AcceptChanges** , чтобы принять все изменения для всей **таблицы DataTable**.  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Управление данными в таблице данных](manipulating-data-in-a-datatable.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
