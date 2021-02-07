---
description: Дополнительные сведения о сопоставлении DataAdapter DataTable и DataColumn
title: Сопоставления DataAdapter DataTable и DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 25007925afa57dd0cb6e75f808444f1bfaeea9b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739740"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Сопоставления DataAdapter DataTable и DataColumn

Объект **DataAdapter** содержит коллекцию из нуля или более <xref:System.Data.Common.DataTableMapping> объектов в своем свойстве **TableMappings** . **Экземпляр DataTableMapping** предоставляет основное сопоставление данных, возвращенных запросом к источнику данных, и <xref:System.Data.DataTable> . Имя **экземпляр DataTableMapping** может быть передано вместо имени **DataTable** в метод **Fill** объекта **DataAdapter**. В следующем примере создается экземпляр класса **DataTableMapping** с именем **AuthorsMapping** для таблицы **Authors**.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Класс **DataTableMapping** позволяет использовать имена столбцов в объекте **DataTable**, отличные от таковых в базе данных. В сопоставлении **DataAdapter** это сопоставление используется для согласования столбцов при обновлении таблицы.  
  
 Если не указан объект **TableName** или имя **DataTableMapping** при вызове метода **Fill** или **Update** объекта **DataAdapter**, то в объекте **DataAdapter** выполняется поиск экземпляра **DataTableMapping** с именем "Table". Если этот **экземпляр DataTableMapping** не существует, то **TableName** объекта **DataTable** имеет значение Table. Можно указать применяемый по умолчанию класс **DataTableMapping** при создании объекта **DataTableMapping** с именем "Table".  
  
 В следующем примере кода создается экземпляр **DataTableMapping** (из пространства имен <xref:System.Data.Common>) и задается в качестве применяемого по умолчанию отображения для указанного объекта **DataAdapter** путем присваивания ему имени "Table". Затем в этом примере столбцы из первой таблицы в результатах запроса (таблицы **Customers** базы данных **Northwind**) сопоставляются с набором понятных для пользователя имен в таблице **Northwind Customers** в <xref:System.Data.DataSet>. Для столбцов, к которым не применяется сопоставление, используются имена столбцов из источника данных.  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 В более сложных ситуациях может быть принято решение, что один и тот же экземпляр **DataAdapter** должен поддерживать загрузку разных таблиц с различными сопоставлениями. Для этого просто добавьте дополнительные объекты **экземпляр DataTableMapping** .  
  
 Если методу **Fill** передается экземпляр **DataSet** и имя **DataTableMapping**, то при наличии сопоставления с этим именем используется это сопоставление; в противном случае используется объект **DataTable** с этим именем.  
  
 В следующих примерах создается экземпляр **DataTableMapping** с именем **Customers** и именем объекта **DataTable**, равным **BizTalkSchema**. Затем в этом примере строки, возвращаемые инструкцией SELECT, сопоставляются с объектом **DataTable**, имеющим имя **BizTalkSchema**.  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
> Если имя исходного столбца не задано для сопоставления столбцов, или имя исходной таблицы не задано для сопоставления таблиц, то автоматически создаются имена, применяемые по умолчанию. Если для сопоставления столбцов не указан исходный столбец, сопоставлению столбцов присваивается добавочное имя по умолчанию **SourceColumn** *N,* начиная с **SourceColumn1**. Если для сопоставления таблицы не указано имя исходной таблицы, сопоставлению таблицы присваивается добавочное имя по умолчанию **SourceTable** *N*, начиная с **SourceTable1**.  
  
> [!NOTE]
> Рекомендуется избегать использования соглашения об именах **SourceColumn** *N* для сопоставления столбцов или **SourceTable** *N* для сопоставления таблиц, поскольку заданное имя может конфликтовать с существующим именем заданного по умолчанию сопоставления столбцов в коллекции **ColumnMappingCollection** или с именем сопоставления таблиц в коллекции **DataTableMappingCollection**. Если указанное имя уже существует, возникает исключение.  
  
## <a name="handling-multiple-result-sets"></a>Обработка нескольких результирующих наборов  

 Если команда **SelectCommand** возвращает несколько таблиц, то в методе **Fill** для таблиц в объекте **DataSet** автоматически формируются имена, которые в качестве суффиксов имеют автоматически увеличивающиеся значения. Значения начинаются с указанного имени таблицы и увеличиваются в форме **TableName** *N*, первым значением является **TableName1**. Можно использовать сопоставления таблиц для сопоставления автоматически создаваемого имени таблицы с тем именем, которое требуется задать для таблицы в объекте **DataSet**. Например, для к команды **SelectCommand**, которая возвращает две таблицы, **Customers** и **Orders**, можно выполнить следующий вызов метода **Fill**.  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 В объекте **DataSet** будут созданы две таблицы: **Customers** и **Customers1**. Можно использовать сопоставления таблиц для обеспечения того, чтобы вторая таблица получила имя **Orders** вместо **Customers1**. Для этого необходимо сопоставить исходную таблицу **Customers1** с таблицей **Orders** из **DataSet**, как показано в следующем примере.  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a>См. также

- [Объекты DataAdapter и DataReader](dataadapters-and-datareaders.md)
- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
