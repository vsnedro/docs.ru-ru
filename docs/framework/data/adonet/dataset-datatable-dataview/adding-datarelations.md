---
title: Добавление отношений DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 5fe2bd45e0abada1f9ec7071e3863da853479b51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202387"
---
# <a name="adding-datarelations"></a><span data-ttu-id="7871e-102">Добавление отношений DataRelation</span><span class="sxs-lookup"><span data-stu-id="7871e-102">Adding DataRelations</span></span>

<span data-ttu-id="7871e-103">В наборе <xref:System.Data.DataSet> с несколькими объектами <xref:System.Data.DataTable> можно использовать объекты <xref:System.Data.DataRelation> для связи таблиц друг с другом, для перехода по таблицам, а также для возвращения дочерних или родительских строк из связанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="7871e-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="7871e-104">Аргументы, необходимые для создания **DataRelation** , — это имя создаваемого объекта **DataRelation** , а также массив из одной или нескольких <xref:System.Data.DataColumn> ссылок на столбцы, которые служат в качестве родительских и дочерних столбцов связи.</span><span class="sxs-lookup"><span data-stu-id="7871e-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="7871e-105">После создания объекта **DataRelation**его можно использовать для перехода между таблицами и получения значений.</span><span class="sxs-lookup"><span data-stu-id="7871e-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="7871e-106">Добавление **DataRelation** в <xref:System.Data.DataSet> добавляет по умолчанию объект <xref:System.Data.UniqueConstraint> в родительскую таблицу и в <xref:System.Data.ForeignKeyConstraint> дочернюю таблицу.</span><span class="sxs-lookup"><span data-stu-id="7871e-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="7871e-107">Дополнительные сведения об этих ограничениях по умолчанию см. в разделе [ограничения DataTable](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="7871e-107">For more information about these default constraints, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="7871e-108">В следующем примере кода создается **отношение DataRelation** с использованием двух <xref:System.Data.DataTable> объектов в <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="7871e-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="7871e-109">Каждый <xref:System.Data.DataTable> содержит столбец с именем **CustID**, который служит связью между двумя <xref:System.Data.DataTable> объектами.</span><span class="sxs-lookup"><span data-stu-id="7871e-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="7871e-110">В примере добавляется единичное **отношение DataRelation** к коллекции **отношений** объекта <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="7871e-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="7871e-111">Первый аргумент в примере указывает имя создаваемого объекта **DataRelation** .</span><span class="sxs-lookup"><span data-stu-id="7871e-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="7871e-112">Второй аргумент задает родительский **столбец** данных, а третий аргумент задает дочерний **столбец**данных.</span><span class="sxs-lookup"><span data-stu-id="7871e-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 <span data-ttu-id="7871e-113">Объект **DataRelation** также имеет **вложенное** свойство, которое, если оно имеет значение **true**, приводит к тому, что строки из дочерней таблицы будут вложены в связанную строку из родительской таблицы при записи в виде XML-элементов с помощью <xref:System.Data.DataSet.WriteXml%2A> .</span><span class="sxs-lookup"><span data-stu-id="7871e-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="7871e-114">Дополнительные сведения см. в статье [Использование XML в наборах данных](using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="7871e-114">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7871e-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7871e-115">See also</span></span>

- [<span data-ttu-id="7871e-116">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="7871e-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="7871e-117">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7871e-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
