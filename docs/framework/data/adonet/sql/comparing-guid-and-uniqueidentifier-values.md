---
title: Сравнение значений идентификатора GUID и uniqueidentifier
description: Узнайте, как создавать и сравнивать значения GUID в .NET Frameworkном поставщике данных для SQL Server, которые представлены типом данных uniqueidentifier.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
ms.openlocfilehash: 245b7246712822043d302c43a765c29ac2090e00
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286511"
---
# <a name="comparing-guid-and-uniqueidentifier-values"></a>Сравнение значений идентификатора GUID и uniqueidentifier
Тип данных глобального уникального идентификатора (GUID) в SQL Server представлен типом данных `uniqueidentifier`, который хранит 16-байтное двоичное значение. GUID — это двоичное число, которое используется в первую очередь как уникальный идентификатор в сети, в которой имеется много компьютеров на множестве сайтов. Идентификаторы GUID могут быть созданы путем вызова функции NEWID в Transact-SQL и гарантированно уникальны во всем мире. Дополнительные сведения см. в статье [uniqueidentifier (Transact-SQL)](/sql/t-sql/data-types/uniqueidentifier-transact-sql).  
  
## <a name="working-with-sqlguid-values"></a>Работа со значениями SqlGuid  
 Так как значения GUID являются длинными и сложными, для пользователей они не имеют смысла. Если случайно сгенерированные идентификаторы GUID используются для ключевых значений и вы вставляете большое количество строк, вы получаете случайные операции ввода-вывода в индексах, что может отрицательно сказаться на производительности. Идентификаторы GUID также относительно велики по сравнению с другими типами данных. В общем случае идентификаторы GUID рекомендуется использовать только в очень ограниченном круге ситуаций, когда ни один другой тип данных не подходит.  
  
### <a name="comparing-guid-values"></a>Сравнение значений GUID  
 Значения `uniqueidentifier` поддерживают операторы сравнения, однако их упорядочивание реализовано без использования поразрядного сравнения. К значению применимы только операции `uniqueidentifier` сравнения (=,  <>, \<, > , \<=, > =) и проверки на NULL (имеет значение NULL и не равно null). Другие арифметические операторы не допускаются.  
  
 Как <xref:System.Guid>, так и <xref:System.Data.SqlTypes.SqlGuid> содержат метод `CompareTo` для сравнения различных значений GUID. Однако `System.Guid.CompareTo` и `SqlTypes.SqlGuid.CompareTo` реализуются по-разному. <xref:System.Data.SqlTypes.SqlGuid> реализует `CompareTo`, используя поведение SQL Server, в последних шести байтах значения, которые являются наиболее значимыми. <xref:System.Guid> вычисляет все 16 байт. Это различие в поведении демонстрируется в следующем примере. В первом фрагменте кода показаны несортированные значения <xref:System.Guid>, а во втором фрагменте показаны отсортированные значения <xref:System.Guid>. В третьем фрагменте показаны отсортированные значения <xref:System.Data.SqlTypes.SqlGuid>. Выходные данные отображаются под листингом кода.  
  
 [!code-csharp[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/VB/source.vb#1)]  
  
 В примере получается следующий вывод.  
  
```output  
Unsorted Guids:  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
  
Sorted Guids:  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
  
Sorted SqlGuids:  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
```  
  
## <a name="see-also"></a>См. также

- [Типы данных SQL Server и ADO.NET](sql-server-data-types.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
