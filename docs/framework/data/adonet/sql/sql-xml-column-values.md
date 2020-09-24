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
# <a name="sql-xml-column-values"></a><span data-ttu-id="25d70-102">Значения столбцов XML SQL</span><span class="sxs-lookup"><span data-stu-id="25d70-102">SQL XML Column Values</span></span>

<span data-ttu-id="25d70-103">В SQL Server поддерживается тип данных `xml`, поэтому разработчики могут получать результирующие наборы с данными этого типа с помощью стандартных средств класса <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="25d70-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="25d70-104">Столбец `xml` может извлекаться как любой другой столбец (например, в <xref:System.Data.SqlClient.SqlDataReader>), но для работы с содержимым столбца в формате XML необходимо использовать <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="25d70-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25d70-105">Пример</span><span class="sxs-lookup"><span data-stu-id="25d70-105">Example</span></span>  

 <span data-ttu-id="25d70-106">В следующем приложении командной строки в экземпляр <xref:System.Data.SqlClient.SqlDataReader> выбираются две строки, каждая из которых содержит столбец `xml`, из таблицы **Sales.Store** базы данных **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="25d70-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="25d70-107">Для каждой строки значение столбца `xml` считывается с помощью метода <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> из <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="25d70-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="25d70-108">Это значение сохраняется в <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="25d70-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="25d70-109">Обратите внимание, что для сохранения содержимого в переменную <xref:System.Data.SqlTypes.SqlXml> необходимо использовать метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>, а не <xref:System.Data.IDataRecord.GetValue%2A>, так как <xref:System.Data.IDataRecord.GetValue%2A> возвращает значение столбца `xml` в формате строки.</span><span class="sxs-lookup"><span data-stu-id="25d70-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25d70-110">Образец базы данных **AdventureWorks** не устанавливается по умолчанию при установке SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25d70-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="25d70-111">Чтобы установить его, запустите программу установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25d70-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="25d70-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="25d70-112">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="25d70-113">XML-данные в SQL Server</span><span class="sxs-lookup"><span data-stu-id="25d70-113">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)
- [<span data-ttu-id="25d70-114">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="25d70-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
