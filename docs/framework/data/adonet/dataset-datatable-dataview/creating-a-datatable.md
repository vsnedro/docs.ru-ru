---
title: Создание таблицы данных
description: Научитесь создавать DataTable в ADO.NET, который представляет одну таблицу реляционных данных в памяти, для использования независимо от других объектов .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 75c9bcf0e0b6180030825b4d1e7dd9e1f9686712
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198643"
---
# <a name="creating-a-datatable"></a>Создание таблицы данных

Объект <xref:System.Data.DataTable>, который представляет одну таблицу находящихся в памяти реляционных данных, может создаваться и использоваться независимо или использоваться другими объектами .NET Framework, чаще всего как член <xref:System.Data.DataSet>.  
  
 Объект **DataTable** можно создать с помощью соответствующего конструктора **DataTable** . Его можно добавить в **набор данных** с помощью метода **Add** , чтобы добавить его в коллекцию **Tables** объекта **DataTable** .  
  
 Объекты **DataTable** можно также создавать в **наборе данных** с помощью методов **Fill** или **FillSchema** объекта **DataAdapter** или из предопределенной или выводимой схемы XML с помощью методов **ReadXml**, **ReadXmlSchema**или **инферксмлсчема** **набора данных**. Обратите внимание, что после добавления **DataTable** в качестве члена коллекции **таблиц** из одного **набора данных**нельзя добавить его в коллекцию таблиц любого другого **набора данных**.  
  
 При первом создании таблицы данных **Таблица**не имеет схемы (то есть структуры). Чтобы определить схему таблицы, необходимо создать и добавить <xref:System.Data.DataColumn> объекты в коллекцию **Columns** таблицы. Кроме того, можно определить первичный ключевой столбец для таблицы, а также создать и добавить объекты **ограничений** в коллекцию **ограничений** таблицы. Определив схему для **DataTable**, можно добавить строки данных в таблицу, добавив объекты **DataRow** в коллекцию **Rows** таблицы.  
  
 При создании таблицы данных значение свойства указывать не обязательно <xref:System.Data.DataTable.TableName%2A> ; свойство можно указать в другое **DataTable**время, либо оставить его пустым. Однако при добавлении таблицы без значения **TableName** в **набор данных**этой таблице будет присвоено добавочное имя по умолчанию таблицы*N*, начинающееся с «Table» для Table0.  
  
> [!NOTE]
> Рекомендуется избегать соглашения об именовании "Table*N*" при указании значения **TableName** , так как указываемое имя может конфликтовать с существующим именем таблицы по умолчанию в **наборе данных**. Если указанное имя уже существует, вызывается исключение.  
  
 В следующем примере создается экземпляр объекта **DataTable** и присваивается имя Customers.  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 В следующем примере создается экземпляр **DataTable** путем его добавления в коллекцию **Tables** **набора данных**.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [DataTables](datatables.md)
- [Заполнение набора данных с помощью адаптера данных DataAdapter](../populating-a-dataset-from-a-dataadapter.md)
- [Загрузка набора данных из XML](loading-a-dataset-from-xml.md)
- [Загрузка сведений о схеме набора данных из XML](loading-dataset-schema-information-from-xml.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
