---
title: Типы SqlType и набор данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: 04f95cd7d3f6e52f644f23dd8a32c77d56a5ddda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147512"
---
# <a name="sqltypes-and-the-dataset"></a>Типы SqlType и набор данных

В ADO.NET 2.0 добавлена поддержка расширенных типов `DataSet` через пространство имен <xref:System.Data.SqlTypes>. Типы в пространстве имен <xref:System.Data.SqlTypes> предназначены для предоставления типов данных с той же семантикой и точностью, которыми обладают типы данных в базе данных SQL Server. Каждый тип данных в пространстве имен <xref:System.Data.SqlTypes> имеет эквивалентный тип данных в SQL Server с аналогичным базовым представлением данных.  
  
 Использование <xref:System.Data.SqlTypes> непосредственно в <xref:System.Data.DataSet> дает несколько преимуществ при работе с типами данных SQL Server. <xref:System.Data.SqlTypes> поддерживает такую же семантику, как и собственные типы данных SQL Server. Указав любой из типов <xref:System.Data.SqlTypes> в определении <xref:System.Data.DataColumn>, вы исключите потерю точности от преобразования типов данных decimal или numeric в типы данных среды CLR.  
  
## <a name="example"></a>Пример  

 В следующем примере создается объект <xref:System.Data.DataTable> с явным определением типов данных <xref:System.Data.DataColumn> при помощи <xref:System.Data.SqlTypes>, а не типов CLR. Этот код заполняет таблицу <xref:System.Data.DataTable> данными из таблицы Sales.SalesOrderDetail базы данных AdventureWorks в SQL Server. Выходные данные, отображаемые в окне консоли, содержат тип данных для каждого столбца и значения, полученные из SQL Server.  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Сопоставления типов данных SQL Server](../sql-server-data-type-mappings.md)
- [Настройка параметров и типы данных параметров](../configuring-parameters-and-parameter-data-types.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
