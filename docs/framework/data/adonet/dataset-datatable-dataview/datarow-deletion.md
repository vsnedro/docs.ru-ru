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
# <a name="datarow-deletion"></a><span data-ttu-id="14fd9-102">Удаление DataRow</span><span class="sxs-lookup"><span data-stu-id="14fd9-102">DataRow Deletion</span></span>

<span data-ttu-id="14fd9-103">Существует два метода, которые можно использовать для удаления <xref:System.Data.DataRow> объекта из <xref:System.Data.DataTable> объекта: метод **Remove** <xref:System.Data.DataRowCollection> объекта и <xref:System.Data.DataRow.Delete%2A> метод объекта **DataRow** .</span><span class="sxs-lookup"><span data-stu-id="14fd9-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="14fd9-104">В то время как <xref:System.Data.DataRowCollection.Remove%2A> метод удаляет **DataRow** из **датаровколлектион**, <xref:System.Data.DataRow.Delete%2A> метод помечает только строку для удаления.</span><span class="sxs-lookup"><span data-stu-id="14fd9-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="14fd9-105">Фактическое удаление происходит, когда приложение вызывает метод **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="14fd9-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="14fd9-106">Использование метода <xref:System.Data.DataRow.Delete%2A> позволяет программно проверять, какие строки помечены для удаления, перед их фактическим удалением.</span><span class="sxs-lookup"><span data-stu-id="14fd9-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="14fd9-107">Когда строка отмечена для удаления, ее свойство <xref:System.Data.DataRow.RowState%2A> имеет значение <xref:System.Data.DataRow.Delete%2A>.</span><span class="sxs-lookup"><span data-stu-id="14fd9-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="14fd9-108">Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не должны вызываться в цикле foreach во время итерации по объекту <xref:System.Data.DataRowCollection>.</span><span class="sxs-lookup"><span data-stu-id="14fd9-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="14fd9-109">Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не изменяет состояние коллекции.</span><span class="sxs-lookup"><span data-stu-id="14fd9-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="14fd9-110">При использовании <xref:System.Data.DataSet> **таблицы** данных или в сочетании с **DataAdapter** и реляционным источником данных используйте метод **Delete** объекта **DataRow** для удаления строки.</span><span class="sxs-lookup"><span data-stu-id="14fd9-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="14fd9-111">Метод **Delete** помечает строку как **удаленную** в **наборе данных** или **DataTable** , но не удаляет ее.</span><span class="sxs-lookup"><span data-stu-id="14fd9-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="14fd9-112">Вместо этого, когда **DataAdapter** обнаруживает строку, помеченную как **Удаленная**, она выполняет метод **DeleteCommand** для удаления строки в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="14fd9-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="14fd9-113">Затем строку можно удалить без возможности восстановления с помощью метода **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="14fd9-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="14fd9-114">При использовании метода **Remove** для удаления строки строка удаляется полностью из таблицы, но **DataAdapter** не удаляет строку в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="14fd9-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="14fd9-115">Метод **Remove** объекта **датаровколлектион** принимает **DataRow** в качестве аргумента и удаляет его из коллекции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="14fd9-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="14fd9-116">В следующем примере показано, как вызвать метод **Delete** для **DataRow** , чтобы изменить его свойство **RowState** на **deleted**.</span><span class="sxs-lookup"><span data-stu-id="14fd9-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="14fd9-117">Если строка помечена для удаления и вызывается метод **AcceptChanges** объекта **DataTable** , то строка удаляется из **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="14fd9-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="14fd9-118">В отличие от этого, при **RejectChanges**вызове RejectChanges **RowState** строки восстанавливается до того, как она была помечена как **Удаленная**.</span><span class="sxs-lookup"><span data-stu-id="14fd9-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14fd9-119">Если **добавляется** **RowState** объекта **DataRow** , то есть он был только что добавлен в таблицу, а затем помечается как **Удаленный**, он удаляется из таблицы.</span><span class="sxs-lookup"><span data-stu-id="14fd9-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14fd9-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="14fd9-120">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="14fd9-121">Управление данными в таблице данных</span><span class="sxs-lookup"><span data-stu-id="14fd9-121">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="14fd9-122">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="14fd9-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
