---
title: Создание DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 539e9763c8aa4affdb6f3bd219a99dbca50cee01
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202347"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="f7c80-102">Создание DataView</span><span class="sxs-lookup"><span data-stu-id="f7c80-102">Creating a DataView</span></span>

<span data-ttu-id="f7c80-103">Есть два способа создания представления данных <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="f7c80-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="f7c80-104">Можно использовать конструктор **DataView** или можно создать ссылку на <xref:System.Data.DataTable.DefaultView%2A> свойство объекта <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="f7c80-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="f7c80-105">Конструктор **DataView** может быть пустым или может принимать либо **DataTable** в виде одного аргумента, либо **DataTable** вместе с условиями фильтра, критерием сортировки и фильтром состояния строки.</span><span class="sxs-lookup"><span data-stu-id="f7c80-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="f7c80-106">Дополнительные сведения о дополнительных аргументах, доступных для использования с **DataView**, см. в разделе [Сортировка и фильтрация данных](sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="f7c80-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="f7c80-107">Поскольку индекс для **DataView** строится как при создании **DataView** , так и при изменении любого из свойств **Sort**, **RowFilter**или **RowStateFilter** , достижение лучшей производительности достигается за счет предоставления любого начального порядка сортировки или критериев фильтрации в качестве аргументов конструктора при создании **DataView**.</span><span class="sxs-lookup"><span data-stu-id="f7c80-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="f7c80-108">Создание **объекта DataView** без указания условия сортировки или фильтра, а затем Установка **свойств Sort**, **RowFilter**или **RowStateFilter** в дальнейшем приводит к тому, что индекс будет построен по крайней мере дважды: один раз при создании **объекта DataView** и при изменении любого свойства сортировки или фильтра.</span><span class="sxs-lookup"><span data-stu-id="f7c80-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="f7c80-109">Обратите внимание, что при создании **DataView** с помощью конструктора, который не принимает никаких аргументов, вы не сможете использовать **DataView** до тех пор, пока не будет задано свойство **Table** .</span><span class="sxs-lookup"><span data-stu-id="f7c80-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="f7c80-110">В следующем примере кода показано, как создать объект **DataView** с помощью конструктора **DataView** .</span><span class="sxs-lookup"><span data-stu-id="f7c80-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="f7c80-111">**RowFilter**, столбец **сортировки** и **DataViewRowState** предоставляются вместе с **таблицей**данных.</span><span class="sxs-lookup"><span data-stu-id="f7c80-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],
    "Country = 'USA'",
    "ContactName",
    DataViewRowState.CurrentRows);  
```  
  
 <span data-ttu-id="f7c80-112">В следующем примере кода показано, как получить ссылку на **представление DataView** по умолчанию объекта **DataTable** с помощью свойства **DefaultView** таблицы.</span><span class="sxs-lookup"><span data-stu-id="f7c80-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7c80-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f7c80-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="f7c80-114">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="f7c80-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="f7c80-115">Сортировка и фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="f7c80-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="f7c80-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="f7c80-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="f7c80-117">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7c80-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
