---
title: Ограничения таблиц данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 1224518a9a16f48f770b6839317b9787da97377b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153278"
---
# <a name="datatable-constraints"></a><span data-ttu-id="2ae6c-102">Ограничения таблиц данных</span><span class="sxs-lookup"><span data-stu-id="2ae6c-102">DataTable Constraints</span></span>

<span data-ttu-id="2ae6c-103">Ограничения позволяют принудительно поддерживать целостность данных <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="2ae6c-104">Ограничение представляет собой автоматическое правило, применяемое к столбцу или связанным столбцам и определяющее порядок действий при каком-либо изменении содержимого строки.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="2ae6c-105">Ограничения применяются, если `System.Data.DataSet.EnforceConstraints` свойство объекта <xref:System.Data.DataSet> имеет **значение true**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="2ae6c-106">Пример кода, показывающий, как установить свойство `EnforceConstraints`, см. в разделе справки <xref:System.Data.DataSet.EnforceConstraints%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="2ae6c-107">В ADO.NET имеется два типа ограничений: <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="2ae6c-108">По умолчанию оба ограничения создаются автоматически при создании связи между двумя или более таблицами путем добавления в <xref:System.Data.DataRelation> **набор данных**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="2ae6c-109">Однако это поведение можно отключить, указав **креатеконстраинтс**  =  **false** при создании связи.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="2ae6c-110">Ограничение ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="2ae6c-110">ForeignKeyConstraint</span></span>  

 <span data-ttu-id="2ae6c-111">**ForeignKeyConstraint** применяет правила, связанные с распространением обновлений и удалений в связанных таблицах.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="2ae6c-112">Например, если значение в строке одной таблицы Обновлено или удалено и это же значение также используется в одной или нескольких связанных таблицах, **ForeignKeyConstraint** определяет, что происходит в связанных таблицах.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="2ae6c-113"><xref:System.Data.ForeignKeyConstraint.DeleteRule%2A>Свойства и <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> объекта **ForeignKeyConstraint** определяют действие, которое должно быть предпринято, когда пользователь пытается удалить или обновить строку в связанной таблице.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="2ae6c-114">В следующей таблице описаны различные параметры, доступные для свойств **DeleteRule** и **UpdateRule** объекта **ForeignKeyConstraint**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="2ae6c-115">Установка правил</span><span class="sxs-lookup"><span data-stu-id="2ae6c-115">Rule setting</span></span>|<span data-ttu-id="2ae6c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="2ae6c-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="2ae6c-117">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="2ae6c-117">**Cascade**</span></span>|<span data-ttu-id="2ae6c-118">Удалить или обновить связанные строки.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="2ae6c-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="2ae6c-119">**SetNull**</span></span>|<span data-ttu-id="2ae6c-120">Задайте **DBNull**значения в связанных строках.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="2ae6c-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="2ae6c-121">**SetDefault**</span></span>|<span data-ttu-id="2ae6c-122">Присвоить столбцам в связанных строках значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="2ae6c-123">**None**</span><span class="sxs-lookup"><span data-stu-id="2ae6c-123">**None**</span></span>|<span data-ttu-id="2ae6c-124">Не выполнять никаких действий в связанных строках.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-124">Take no action on related rows.</span></span> <span data-ttu-id="2ae6c-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-125">This is the default.</span></span>|  
  
 <span data-ttu-id="2ae6c-126">**ForeignKeyConstraint** может ограничивать, а также распространять изменения в связанных столбцах.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="2ae6c-127">В зависимости от свойств, заданных для объекта **ForeignKeyConstraint** столбца, если свойство **енфорцеконстраинтс** **набора данных** имеет **значение true**, выполнение определенных операций в родительской строке приведет к исключению.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="2ae6c-128">Например, **Если свойство объекта** **ForeignKeyConstraint** имеет значение **None**, то родительская строка не может быть удалена, если она содержит дочерние строки.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="2ae6c-129">Ограничение внешнего ключа можно создать между отдельными столбцами или между массивами столбцов с помощью конструктора **ForeignKeyConstraint** .</span><span class="sxs-lookup"><span data-stu-id="2ae6c-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="2ae6c-130">Передайте полученный объект **ForeignKeyConstraint** методу **Add** свойства Table **rechecks** , который является **констраинтколлектион**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="2ae6c-131">Можно также передать аргументы конструктора в несколько перегрузок метода **Add** объекта **констраинтколлектион** , чтобы создать объект **ForeignKeyConstraint**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="2ae6c-132">При создании **ForeignKeyConstraint**можно передать значения **DeleteRule** и **UpdateRule** в конструктор в качестве аргументов или задать их в качестве свойств, как показано в следующем примере (где значение **DeleteRule** равно **None**).</span><span class="sxs-lookup"><span data-stu-id="2ae6c-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a><span data-ttu-id="2ae6c-133">Свойство AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="2ae6c-133">AcceptRejectRule</span></span>  

 <span data-ttu-id="2ae6c-134">Изменения в строках могут быть приняты с помощью метода **AcceptChanges** или отменены с помощью метода **RejectChanges** **набора данных**, **DataTable**или **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="2ae6c-135">Если **набор данных** содержит **фореигнкэйконстраинтс**, вызов методов **AcceptChanges** или **RejectChanges** применяет **акцептрежектруле**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="2ae6c-136">Свойство **акцептрежектруле** объекта **ForeignKeyConstraint** определяет, какое действие будет выполнено с дочерними строками при вызове **метода AcceptChanges** или **RejectChanges** в родительской строке.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="2ae6c-137">В следующей таблице перечислены доступные параметры для **акцептрежектруле**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="2ae6c-138">Установка правил</span><span class="sxs-lookup"><span data-stu-id="2ae6c-138">Rule setting</span></span>|<span data-ttu-id="2ae6c-139">Описание</span><span class="sxs-lookup"><span data-stu-id="2ae6c-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="2ae6c-140">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="2ae6c-140">**Cascade**</span></span>|<span data-ttu-id="2ae6c-141">Принять или отклонить изменения в дочерних строках.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="2ae6c-142">**None**</span><span class="sxs-lookup"><span data-stu-id="2ae6c-142">**None**</span></span>|<span data-ttu-id="2ae6c-143">Не выполнять никаких действий в дочерних строках.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-143">Take no action on child rows.</span></span> <span data-ttu-id="2ae6c-144">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="2ae6c-145">Пример</span><span class="sxs-lookup"><span data-stu-id="2ae6c-145">Example</span></span>  

 <span data-ttu-id="2ae6c-146">В следующем примере создается ограничение <xref:System.Data.ForeignKeyConstraint>, устанавливаются некоторые из его свойств, в том числе <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, а само ограничение добавляется в коллекцию <xref:System.Data.ConstraintCollection> объекта <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="2ae6c-147">Ограничение UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="2ae6c-147">UniqueConstraint</span></span>  

 <span data-ttu-id="2ae6c-148">Объект **UniqueConstraint** , который может быть назначен одному столбцу или массиву столбцов в **DataTable**, гарантирует, что все данные в указанном столбце или столбцах уникальны для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="2ae6c-149">Можно создать ограничение уникальности для столбца или массива столбцов с помощью конструктора **UniqueConstraint** .</span><span class="sxs-lookup"><span data-stu-id="2ae6c-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="2ae6c-150">Передайте полученный объект **UniqueConstraint** в метод **Add** свойства **ограничения** таблицы, которое является **констраинтколлектион**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="2ae6c-151">Можно также передать аргументы конструктора в несколько перегрузок метода **Add** объекта **констраинтколлектион** , чтобы создать **UniqueConstraint**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="2ae6c-152">При создании **UniqueConstraint** для столбца или столбцов можно дополнительно указать, является ли столбец или столбцы первичным ключом.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="2ae6c-153">Можно также создать ограничение уникальности для столбца, задав свойству **UNIQUE** столбца **значение true**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="2ae6c-154">Кроме того, если задать для свойства **UNIQUE** одного столбца значение **false** , то все ограничения уникальности, которые могут существовать, будут удалены.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="2ae6c-155">При определении столбца или группы столбцов в качестве первичного ключа таблицы автоматически создается ограничение уникальности для заданного столбца или группы столбцов.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="2ae6c-156">Если удалить столбец из свойства **PrimaryKey** объекта **DataTable**, **UniqueConstraint** будет удален.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="2ae6c-157">В следующем примере создается **UniqueConstraint** для двух столбцов **таблицы DataTable**.</span><span class="sxs-lookup"><span data-stu-id="2ae6c-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]
    {custTable.Columns["CustomerID"],
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ae6c-158">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2ae6c-158">See also</span></span>

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [<span data-ttu-id="2ae6c-159">Определение схемы таблицы данных</span><span class="sxs-lookup"><span data-stu-id="2ae6c-159">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="2ae6c-160">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="2ae6c-160">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="2ae6c-161">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2ae6c-161">ADO.NET Overview</span></span>](../ado-net-overview.md)
