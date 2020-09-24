---
title: Значения столбцов XML SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: cd55e2263d4b71fe62910ac918e331ebe37833eb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177284"
---
# <a name="sql-xml-column-values"></a>Значения столбцов XML SQL

В SQL Server поддерживается тип данных `xml`, поэтому разработчики могут получать результирующие наборы с данными этого типа с помощью стандартных средств класса <xref:System.Data.SqlClient.SqlCommand>. Столбец `xml` может извлекаться как любой другой столбец (например, в <xref:System.Data.SqlClient.SqlDataReader>), но для работы с содержимым столбца в формате XML необходимо использовать <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Пример  

 В следующем приложении командной строки в экземпляр <xref:System.Data.SqlClient.SqlDataReader> выбираются две строки, каждая из которых содержит столбец `xml`, из таблицы **Sales.Store** базы данных **AdventureWorks**. Для каждой строки значение столбца `xml` считывается с помощью метода <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> из <xref:System.Data.SqlClient.SqlDataReader>. Это значение сохраняется в <xref:System.Xml.XmlReader>. Обратите внимание, что для сохранения содержимого в переменную <xref:System.Data.SqlTypes.SqlXml> необходимо использовать метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>, а не <xref:System.Data.IDataRecord.GetValue%2A>, так как <xref:System.Data.IDataRecord.GetValue%2A> возвращает значение столбца `xml` в формате строки.  
  
> [!NOTE]
> Образец базы данных **AdventureWorks** не устанавливается по умолчанию при установке SQL Server. Чтобы установить его, запустите программу установки SQL Server.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.SqlTypes.SqlXml>
- [XML-данные в SQL Server](xml-data-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
