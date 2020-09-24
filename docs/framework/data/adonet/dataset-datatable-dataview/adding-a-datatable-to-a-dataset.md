---
title: Добавление новой таблицы данных в набор данных
description: Ознакомьтесь с этим примером кода, чтобы узнать, как создавать объекты DataTable и добавлять их в существующий набор данных в ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: 6a5e3a89870b3959a6ac042b93414694e8a6cc1c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164900"
---
# <a name="adding-a-datatable-to-a-dataset"></a><span data-ttu-id="94d39-103">Добавление новой таблицы данных в набор данных</span><span class="sxs-lookup"><span data-stu-id="94d39-103">Adding a DataTable to a DataSet</span></span>

<span data-ttu-id="94d39-104">ADO.NET позволяет создавать объекты <xref:System.Data.DataTable> и добавлять их к существующему <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="94d39-104">ADO.NET enables you to create <xref:System.Data.DataTable> objects and add them to an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="94d39-105">Можно задать данные ограничения для <xref:System.Data.DataTable>, используя свойства <xref:System.Data.DataTable.PrimaryKey%2A> и <xref:System.Data.DataColumn.Unique%2A>.</span><span class="sxs-lookup"><span data-stu-id="94d39-105">You can set constraint information for a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.PrimaryKey%2A> and <xref:System.Data.DataColumn.Unique%2A> properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94d39-106">Пример</span><span class="sxs-lookup"><span data-stu-id="94d39-106">Example</span></span>  

 <span data-ttu-id="94d39-107">Следующий пример показывает, как создать объект <xref:System.Data.DataSet>, добавить новый объект <xref:System.Data.DataTable> к <xref:System.Data.DataSet>, а затем добавить к таблице три объекта <xref:System.Data.DataColumn>.</span><span class="sxs-lookup"><span data-stu-id="94d39-107">The following example constructs a <xref:System.Data.DataSet>, adds a new <xref:System.Data.DataTable> object to the <xref:System.Data.DataSet>, and then adds three <xref:System.Data.DataColumn> objects to the table.</span></span> <span data-ttu-id="94d39-108">В конце код задает один столбец в качестве столбца первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="94d39-108">Finally, the code sets one column as the primary key column.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a><span data-ttu-id="94d39-109">Чувствительность к регистру</span><span class="sxs-lookup"><span data-stu-id="94d39-109">Case Sensitivity</span></span>  

 <span data-ttu-id="94d39-110">В <xref:System.Data.DataSet> могут существовать две или несколько таблиц или связей, имеющие одинаковые имена, которые, тем не менее, состоят из символов с разными регистрами.</span><span class="sxs-lookup"><span data-stu-id="94d39-110">Two or more tables or relations with the same name, but different casing, can exist in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="94d39-111">В таких случаях ссылки по имени на таблицы и связи задаются с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="94d39-111">In such cases, references by name to tables and relations are case sensitive.</span></span> <span data-ttu-id="94d39-112">Например, если <xref:System.Data.DataSet> **набор данных** содержит таблицы **Table1** и **Table1**, вы бы ссылались на таблицу **Table1** по имени как **DataSet. Tables ["table1"]** и **Table1** в качестве **набора данных. Tables ["table1"]**.</span><span class="sxs-lookup"><span data-stu-id="94d39-112">For example, if the <xref:System.Data.DataSet> **dataSet** contains tables **Table1** and **table1**, you would reference **Table1** by name as **dataSet.Tables["Table1"]**, and **table1** as **dataSet.Tables["table1"]**.</span></span> <span data-ttu-id="94d39-113">Попытка ссылки на любую из таблиц в качестве **набора данных. таблицы ["table1"]** создают исключение.</span><span class="sxs-lookup"><span data-stu-id="94d39-113">Attempting to reference either of the tables as **dataSet.Tables["TABLE1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="94d39-114">Это правило учета регистра не применяется, если только одна таблица или связь имеет какое-то определенное имя.</span><span class="sxs-lookup"><span data-stu-id="94d39-114">The case-sensitivity behavior does not apply if only one table or relation has a particular name.</span></span> <span data-ttu-id="94d39-115">Например, если <xref:System.Data.DataSet> имеет только **Таблица1**, можно ссылаться на него с помощью **DataSet. Tables ["table1"]**.</span><span class="sxs-lookup"><span data-stu-id="94d39-115">For example, if the <xref:System.Data.DataSet> has only **Table1**, you can reference it using **dataSet.Tables["TABLE1"]**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94d39-116">Указанное правило применяется без учета значения свойства <xref:System.Data.DataSet.CaseSensitive%2A> объекта <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="94d39-116">The <xref:System.Data.DataSet.CaseSensitive%2A> property of the <xref:System.Data.DataSet> does not affect this behavior.</span></span> <span data-ttu-id="94d39-117">Свойство <xref:System.Data.DataSet.CaseSensitive%2A> применяется к данным в <xref:System.Data.DataSet> и затрагивает сортировку, поиск, фильтрацию, предписание ограничений и т. д.</span><span class="sxs-lookup"><span data-stu-id="94d39-117">The <xref:System.Data.DataSet.CaseSensitive%2A> property applies to the data in the <xref:System.Data.DataSet> and affects sorting, searching, filtering, enforcing constraints, and so on.</span></span>  
  
## <a name="namespace-support"></a><span data-ttu-id="94d39-118">Поддержка пространства имен</span><span class="sxs-lookup"><span data-stu-id="94d39-118">Namespace Support</span></span>  

 <span data-ttu-id="94d39-119">В версиях ADO.NET, выпущенных до версии 2.0, две таблицы не могли иметь одинаковое имя, даже если находились в разных пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="94d39-119">In versions of ADO.NET earlier than 2.0, two tables could not have the same name, even if they were in different namespaces.</span></span> <span data-ttu-id="94d39-120">Это ограничение было снято в ADO.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="94d39-120">This limitation was removed in ADO.NET 2.0.</span></span> <span data-ttu-id="94d39-121">Набор данных <xref:System.Data.DataSet> может содержать две таблицы, имеющие одинаковое значение свойства <xref:System.Data.DataTable.TableName%2A>, но различные значения свойства <xref:System.Data.DataTable.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="94d39-121">A <xref:System.Data.DataSet> can contain two tables that have the same <xref:System.Data.DataTable.TableName%2A> property value but different <xref:System.Data.DataTable.Namespace%2A> property values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94d39-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="94d39-122">See also</span></span>

- [<span data-ttu-id="94d39-123">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="94d39-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="94d39-124">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="94d39-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
