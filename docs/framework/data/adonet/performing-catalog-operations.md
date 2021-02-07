---
description: 'Дополнительные сведения: выполнение операций с каталогами'
title: Выполнение операций каталога
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: c484e3a56d846de66c6e13b374efe58430ab86b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754346"
---
# <a name="performing-catalog-operations"></a>Выполнение операций каталога

Чтобы выполнить команду изменения базы данных или каталога, такую как инструкция CREATE TABLE или CREATE PROCEDURE, создайте объект **Command** с помощью соответствующих инструкций SQL и объекта **Connection**. Выполните команду с помощью метода **ExecuteNonQuery** объекта **Command** .  
  
 В следующем примере кода создается хранимая процедура в базе данных Microsoft SQL Server.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a>См. также

- [Использование команд для изменения данных](using-commands-to-modify-data.md)
- [Команды и параметры](commands-and-parameters.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
