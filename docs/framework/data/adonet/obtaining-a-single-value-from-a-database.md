---
title: Получение одного значения из базы данных
description: Узнайте, как вернуть одно значение в ADO.NET. В этом примере кода возвращается значение столбца идентификаторов для вставленной записи.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 9ce29bc1321814bd60cfaacd222fc55a3fbf12ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150730"
---
# <a name="obtaining-a-single-value-from-a-database"></a>Получение одного значения из базы данных

Может возникнуть необходимость вернуть сведения из базы данных, которые представляют собой одиночное значение, а не форму таблицы или поток данных. Например, может потребоваться возврат результата агрегатной функции, такой как COUNT ( \* ), Sum (Price) или AVG (Quantity). Объект **Command** предоставляет возможность возвращать одиночные значения с помощью метода **ExecuteScalar** . Метод **ExecuteScalar** возвращает, как скалярное значение, значение первого столбца первой строки результирующего набора.  
  
 В следующем примере кода в базу данных при помощи <xref:System.Data.SqlClient.SqlCommand> вставляется новое значение. Метод <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> используется, чтобы вернуть значение столбца идентификатора для вставленной записи.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Команды и параметры](commands-and-parameters.md)
- [Выполнение команды](executing-a-command.md)
- [DbConnection, DbCommand и DbException](dbconnection-dbcommand-and-dbexception.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
