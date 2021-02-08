---
description: Дополнительные сведения о значениях столбцов SQL XML
title: Значения столбцов XML SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 357d55e2ce497c9929b8e7e7459ebf23ccaafede
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767184"
---
# <a name="sql-xml-column-values"></a>Значения столбцов XML SQL

В SQL Server поддерживается тип данных `xml`, поэтому разработчики могут получать результирующие наборы с данными этого типа с помощью стандартных средств класса <xref:System.Data.SqlClient.SqlCommand>. Столбец `xml` может извлекаться как любой другой столбец (например, в <xref:System.Data.SqlClient.SqlDataReader>), но для работы с содержимым столбца в формате XML необходимо использовать <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Пример  

 В следующем приложении командной строки в экземпляр `xml` выбираются две строки, каждая из которых содержит столбец **, из таблицы** Sales.Store **базы данных** AdventureWorks<xref:System.Data.SqlClient.SqlDataReader>. Для каждой строки значение столбца `xml` считывается с помощью метода <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> из <xref:System.Data.SqlClient.SqlDataReader>. Это значение сохраняется в <xref:System.Xml.XmlReader>. Обратите внимание, что для сохранения содержимого в переменную <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> необходимо использовать метод <xref:System.Data.IDataRecord.GetValue%2A>, а не <xref:System.Data.SqlTypes.SqlXml>, так как <xref:System.Data.IDataRecord.GetValue%2A> возвращает значение столбца `xml` в формате строки.  
  
> [!NOTE]
> Образец базы данных **AdventureWorks** не устанавливается по умолчанию при установке SQL Server. Чтобы установить его, запустите программу установки SQL Server.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.SqlTypes.SqlXml>
- [XML-данные в SQL Server](xml-data-in-sql-server.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
