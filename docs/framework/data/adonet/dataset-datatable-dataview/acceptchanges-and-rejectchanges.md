---
title: AcceptChanges и RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: e29d2404d6d593b9a5b905206af3cdd3bc1a3e51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177596"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="f2cbb-102">AcceptChanges и RejectChanges</span><span class="sxs-lookup"><span data-stu-id="f2cbb-102">AcceptChanges and RejectChanges</span></span>

<span data-ttu-id="f2cbb-103">После проверки точности изменений, внесенных в данные в <xref:System.Data.DataTable> , можно принять изменения с помощью <xref:System.Data.DataRow.AcceptChanges%2A> метода <xref:System.Data.DataRow> , <xref:System.Data.DataTable> или <xref:System.Data.DataSet> , который установит **текущие** значения строк в качестве **исходных** значений, и установит для свойства **RowState** значение **без изменений**.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="f2cbb-104">При принятии или отклонении изменений удаляется любая **роверрор** информация, а свойству **HasErrors** присваивается **значение false**.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="f2cbb-105">Принятие или отклонение изменений также может затрагивать обновление данных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="f2cbb-106">Дополнительные сведения см. в разделе [Обновление источников данных с помощью DataAdapter](../updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="f2cbb-106">For more information, see [Updating Data Sources with DataAdapters](../updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="f2cbb-107">Если в **DataTable**существуют ограничения внешнего ключа, изменения, принятые или Отклоненные с помощью **AcceptChanges** и **RejectChanges** , распространяются на дочерние строки **DataRow** в соответствии с объектом **ForeignKeyConstraint. акцептрежектруле**.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="f2cbb-108">Дополнительные сведения см. в разделе [ограничения DataTable](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="f2cbb-108">For more information, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="f2cbb-109">В следующем примере происходит проверка на наличие строк с ошибками, по возможности устраняются ошибки и отклоняются строки, в которых ошибка не может быть устранена.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="f2cbb-110">Обратите внимание, что для разрешенных ошибок значение **роверрор** сбрасывается в пустую строку, в результате чего свойство **HasErrors** устанавливается в значение **false**.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="f2cbb-111">Если все строки с ошибками были разрешены или отклонены, вызывается метод **AcceptChanges** , чтобы принять все изменения для всей **таблицы DataTable**.</span><span class="sxs-lookup"><span data-stu-id="f2cbb-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f2cbb-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f2cbb-112">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="f2cbb-113">Управление данными в таблице данных</span><span class="sxs-lookup"><span data-stu-id="f2cbb-113">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="f2cbb-114">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f2cbb-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
