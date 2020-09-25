---
title: Подключение к источнику данных
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: b9e69b029ad37c583e51c219f87ff9d7d8e7315c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203778"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Подключение к источнику данных в ADO.NET

В ADO.NET объект **Connection** используется для подключения к определенному источнику данных путем предоставления необходимых сведений о проверке подлинности в строке подключения. Используемый объект **соединения** зависит от типа источника данных.  
  
 Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объект <xref:System.Data.Common.DbConnection>: поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbConnection>, поставщик данных .NET Framework для SQL Server содержит объект <xref:System.Data.SqlClient.SqlConnection>, поставщик данных .NET Framework для ODBC содержит объект <xref:System.Data.Odbc.OdbcConnection>, поставщик данных .NET Framework для Oracle содержит объект <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Установка подключения](establishing-the-connection.md)\
 Описывает использование объекта **Connection** для установления соединения с источником данных.  
  
 [События подключения](connection-events.md)\
 Описывает использование события **InfoMessage** для получения информационных сообщений из источника данных.  
  
## <a name="see-also"></a>См. также раздел

- [Строки подключения](connection-strings.md)
- [Объединение подключений в пул](connection-pooling.md)
- [Команды и параметры](commands-and-parameters.md)
- [Объекты DataAdapter и DataReader](dataadapters-and-datareaders.md)
- [Транзакции и параллельность](transactions-and-concurrency.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
