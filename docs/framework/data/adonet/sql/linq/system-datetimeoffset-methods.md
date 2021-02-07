---
description: Дополнительные сведения о методах System. DateTimeOffset
title: Методы System.DateTimeOffset
ms.date: 03/30/2017
ms.assetid: 25b3e5c0-7603-4a70-b3e5-2149e3da69a2
ms.openlocfilehash: 050c710d4a3f3db8112d0d108338c010345afdda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681334"
---
# <a name="systemdatetimeoffset-methods"></a>Методы System.DateTimeOffset

После их сопоставления в модели объектов или внешнем файле сопоставления LINQ to SQL позволяет использовать большинство методов, операторов и свойств <xref:System.DateTimeOffset?displayProperty=nameWithType> внутри запросов LINQ to SQL.  
  
 Не поддерживаются только те методы, которые унаследованы от <xref:System.Object?displayProperty=nameWithType> и не имеют смысла в контексте запросов LINQ to SQL, например `Finalize`, `GetHashCode`, `GetType` и `MemberwiseClone`. Эти методы не поддерживаются, поскольку LINQ to SQL не может перевести их для выполнения в SQL Server.  
  
> [!NOTE]
> Для структуры среды CLR <xref:System.DateTimeOffset?displayProperty=nameWithType> и для обеспечения возможности ее сопоставления столбцу SQL `DATETIMEOFFSET` с помощью LINQ to SQL необходима платформа .NET Framework 3.5 с пакетом обновления 1 (SP1) или выше. Столбец SQL типа `DATETIMEOFFSET` доступен только в версиях Microsoft SQL Server 2008 и выше.  
  
## <a name="sqlmethods-date-and-time-methods"></a>Методы даты и времени класса SQLMethods  

 Помимо методов, содержащихся в структуре <xref:System.DateTimeOffset>, LINQ to SQL поддерживает методы для работы с датой и временем из класса <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType>, перечисленные в следующей таблице.  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a>См. также

- [Основные принципы запросов](query-concepts.md)
- [Создание модели объектов](creating-the-object-model.md)
- [Сопоставление типов SQL-CLR](sql-clr-type-mapping.md)
