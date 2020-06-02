---
title: Получение одного значения из базы данных
description: Узнайте, как вернуть одно значение в ADO.NET. В этом примере кода возвращается значение столбца идентификаторов для вставленной записи.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: a6f268f72f8b8a09ae48ba3cad6254323cb95a20
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286706"
---
# <a name="obtaining-a-single-value-from-a-database"></a>Получение одного значения из базы данных
Может возникнуть необходимость вернуть сведения из базы данных, которые представляют собой одиночное значение, а не форму таблицы или поток данных. Например, может потребоваться возврат результата агрегатной функции, такой как COUNT ( \* ), Sum (Price) или AVG (Quantity). Объект **Command** предоставляет возможность возвращать одиночные значения с помощью метода **ExecuteScalar** . Метод **ExecuteScalar** возвращает, как скалярное значение, значение первого столбца первой строки результирующего набора.  
  
 В следующем примере кода в базу данных при помощи <xref:System.Data.SqlClient.SqlCommand> вставляется новое значение. Метод <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> используется, чтобы вернуть значение столбца идентификатора для вставленной записи.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Команды и параметры](commands-and-parameters.md)
- [Исполнение команды](executing-a-command.md)
- [DbConnection, DbCommand и DbException](dbconnection-dbcommand-and-dbexception.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
