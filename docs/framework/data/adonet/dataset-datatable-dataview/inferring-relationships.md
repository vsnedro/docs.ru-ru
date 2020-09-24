---
title: Определение отношений
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: ee691eee95c34afdb6374cdd7448d4b44ece3055
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177570"
---
# <a name="inferring-relationships"></a><span data-ttu-id="c5e99-102">Определение отношений</span><span class="sxs-lookup"><span data-stu-id="c5e99-102">Inferring Relationships</span></span>

<span data-ttu-id="c5e99-103">Если элемент, выводимый в виде таблицы, имеет дочерний элемент, который также выводится в виде таблицы, между двумя этими таблицами будет создана связь <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="c5e99-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="c5e99-104">Новый столбец с именем **ParentTableName_Id** будет добавлен как в таблицу, созданную для родительского элемента, так и на таблицу, созданную для дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="c5e99-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="c5e99-105">Свойству **ColumnMapping** этого столбца идентификаторов будет присвоено значение **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="c5e99-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="c5e99-106">Столбец будет автоматически инкрементным первичным ключом для родительской таблицы и будет использоваться для **связи DataRelation** между двумя таблицами.</span><span class="sxs-lookup"><span data-stu-id="c5e99-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="c5e99-107">Тип данных добавленного столбца идентификаторов будет **System. Int32**, в отличие от типа данных всех других выводимых столбцов, которые имеют тип **System. String**.</span><span class="sxs-lookup"><span data-stu-id="c5e99-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="c5e99-108">Объект <xref:System.Data.ForeignKeyConstraint> с **DeleteRule**  =  **CASCADE** также будет создан с помощью нового столбца как в родительской, так и в дочерней таблице.</span><span class="sxs-lookup"><span data-stu-id="c5e99-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="c5e99-109">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="c5e99-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="c5e99-110">Процесс вывода приведет к созданию двух таблиц: **Element1** и **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="c5e99-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="c5e99-111">Таблица **Element1** будет содержать два столбца: **Element1_Id** и **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="c5e99-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="c5e99-112">Свойству **ColumnMapping** столбца **Element1_Id** будет присвоено значение **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="c5e99-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="c5e99-113">Свойству **ColumnMapping** столбца **ChildElement2** будет присвоено значение **MappingType. element**.</span><span class="sxs-lookup"><span data-stu-id="c5e99-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="c5e99-114">Столбец **Element1_Id** будет установлен в качестве первичного ключа таблицы **Element1** .</span><span class="sxs-lookup"><span data-stu-id="c5e99-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="c5e99-115">Таблица **ChildElement1** будет содержать три столбца: **attr1**, **attr2** и **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="c5e99-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="c5e99-116">Свойству **ColumnMapping** для столбцов **attr1** и **attr2** будет присвоено значение **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="c5e99-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="c5e99-117">Свойству **ColumnMapping** столбца **Element1_Id** будет присвоено значение **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="c5e99-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="c5e99-118">**DataRelation** и **ForeignKeyConstraint** будут созданы с использованием **Element1_Id** столбцов из обеих таблиц.</span><span class="sxs-lookup"><span data-stu-id="c5e99-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="c5e99-119">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="c5e99-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="c5e99-120">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="c5e99-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="c5e99-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="c5e99-121">Element1_Id</span></span>|<span data-ttu-id="c5e99-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="c5e99-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="c5e99-123">0</span><span class="sxs-lookup"><span data-stu-id="c5e99-123">0</span></span>|<span data-ttu-id="c5e99-124">Text2</span><span class="sxs-lookup"><span data-stu-id="c5e99-124">Text2</span></span>|  
  
 <span data-ttu-id="c5e99-125">**Таблица:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="c5e99-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="c5e99-126">attr1</span><span class="sxs-lookup"><span data-stu-id="c5e99-126">attr1</span></span>|<span data-ttu-id="c5e99-127">attr2</span><span class="sxs-lookup"><span data-stu-id="c5e99-127">attr2</span></span>|<span data-ttu-id="c5e99-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="c5e99-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="c5e99-129">value1</span><span class="sxs-lookup"><span data-stu-id="c5e99-129">value1</span></span>|<span data-ttu-id="c5e99-130">value2</span><span class="sxs-lookup"><span data-stu-id="c5e99-130">value2</span></span>|<span data-ttu-id="c5e99-131">0</span><span class="sxs-lookup"><span data-stu-id="c5e99-131">0</span></span>|  
  
 <span data-ttu-id="c5e99-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="c5e99-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="c5e99-133">**Паренттабле:** Element1</span><span class="sxs-lookup"><span data-stu-id="c5e99-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="c5e99-134">**Парентколумн:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="c5e99-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="c5e99-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="c5e99-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="c5e99-136">**Чилдколумн:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="c5e99-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="c5e99-137">**Вложенные:** Условия</span><span class="sxs-lookup"><span data-stu-id="c5e99-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="c5e99-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="c5e99-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="c5e99-139">**Столбец:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="c5e99-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="c5e99-140">**Паренттабле:** Element1</span><span class="sxs-lookup"><span data-stu-id="c5e99-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="c5e99-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="c5e99-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="c5e99-142">**DeleteRule:** Аргумент</span><span class="sxs-lookup"><span data-stu-id="c5e99-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="c5e99-143">**Акцептрежектруле:** None</span><span class="sxs-lookup"><span data-stu-id="c5e99-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e99-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c5e99-144">See also</span></span>

- [<span data-ttu-id="c5e99-145">Определение реляционной структуры набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="c5e99-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="c5e99-146">Загрузка набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="c5e99-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="c5e99-147">Загрузка сведений о схеме набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="c5e99-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="c5e99-148">Вложение отношений DataRelation</span><span class="sxs-lookup"><span data-stu-id="c5e99-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="c5e99-149">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="c5e99-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="c5e99-150">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="c5e99-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c5e99-151">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c5e99-151">ADO.NET Overview</span></span>](../ado-net-overview.md)
