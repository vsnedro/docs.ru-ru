---
description: 'Дополнительные сведения: создание столбцов выражений'
title: Создание столбцов выражений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 96b445734d645a957951a1d4cbd9d72ed254068f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724990"
---
# <a name="creating-expression-columns"></a>Создание столбцов выражений

Можно определить выражение для столбца, позволяя тем самым хранить в нем значение, вычисляемое из значений других столбцов той же строки или из значений столбцов нескольких строк таблицы. Для определения вычисляемого выражения используется свойство <xref:System.Data.DataColumn.Expression%2A> целевого столбца, свойство <xref:System.Data.DataColumn.ColumnName%2A> - для ссылки на другие столбцы в выражении. Тип данных <xref:System.Data.DataColumn.DataType%2A> столбца выражения должен соответствовать типу данных значения, возвращаемого выражением.  
  
 В следующей таблице приведен список возможного использования столбцов выражений в таблице.  
  
|Тип выражения|Пример|  
|---------------------|-------------|  
|Сравнение|"Всего >= 500"|  
|Вычисление|"UnitPrice * Quantity"|  
|Агрегирование|Sum(Price)|  
  
 Можно задать свойство **Expression** для существующего объекта **DataColumn** или включить свойство в качестве третьего аргумента, передаваемого <xref:System.Data.DataColumn> конструктору, как показано в следующем примере.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 Выражение может содержать ссылки на другие столбцы выражений, но циклическая ссылка, при которой два выражения ссылаются друг на друга, вызовет исключение. Правила написания выражений см. в описании <xref:System.Data.DataColumn.Expression%2A> Свойства класса **DataColumn** .  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Определение схемы таблицы данных](datatable-schema-definition.md)
- [DataTables](datatables.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
