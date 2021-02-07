---
description: 'Дополнительные сведения: создание столбцов с автоувеличением'
title: Создание столбцов AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 7568b1013b7af5aef7a6fc1f28dc163a082743a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739642"
---
# <a name="creating-autoincrement-columns"></a>Создание столбцов AutoIncrement

Чтобы обеспечить наличие в столбце уникальных значений, можно указать, что значения в столбце должны увеличиваться автоматически при добавлении новых строк к таблице. Чтобы создать автоматическое приращение <xref:System.Data.DataColumn> , присвойте <xref:System.Data.DataColumn.AutoIncrement%2A> свойству столбца значение **true**. <xref:System.Data.DataColumn>Затем начинается со значения, определенного в <xref:System.Data.DataColumn.AutoIncrementSeed%2A> свойстве, и при добавлении каждой строки значение столбца **AutoIncrement** увеличивается на значение, определенное в <xref:System.Data.DataColumn.AutoIncrementStep%2A> свойстве столбца.  
  
 Для столбцов с **автоувеличением** рекомендуется, <xref:System.Data.DataColumn.ReadOnly%2A> чтобы свойство **DataColumn** было установлено в **значение true**.  
  
 В следующем примере показано, как создать столбец, значения в котором начинаются с 200 и каждый раз увеличиваются с шагом 3.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataColumn>
- [Определение схемы таблицы данных](datatable-schema-definition.md)
- [DataTables](datatables.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
