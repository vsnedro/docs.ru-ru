---
title: Использование команд для изменения данных
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: e2f61dbf74f28d026ae91a2bc8f5bb78530ffeac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177258"
---
# <a name="using-commands-to-modify-data"></a>Использование команд для изменения данных

Используя поставщик данных .NET Framework, можно выполнять хранимые процедуры или инструкции языка описания данных DDL (например, CREATE TABLE и ALTER COLUMN) для выполнения операций со схемой в базе данных или в каталоге. Эти команды не возвращают строки в виде запроса, поэтому объект **Command** предоставляет **ExecuteNonQuery** для их обработки.  
  
 Кроме использования функции **ExecuteNonQuery** для изменения схемы, этот метод можно также использовать для обработки инструкций SQL, которые изменяют данные, но не возвращают строки, такие как INSERT, Update и DELETE.  
  
 Хотя метод **ExecuteNonQuery** не возвращает строки, входные и выходные параметры и возвращаемые значения могут передаваться и возвращаться через коллекцию **Parameters** объекта **Command** .  
  
## <a name="in-this-section"></a>в этом разделе  

 [Обновление данных в источнике данных](updating-data-in-a-data-source.md)  
 Описывает выполнение команд или хранимых процедур, которые изменяют данные в базе данных.  
  
 [Выполнение операций каталога](performing-catalog-operations.md)  
 Описывает выполнение команд, которые изменяют схему базы данных.  
  
## <a name="see-also"></a>См. также раздел

- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Команды и параметры](commands-and-parameters.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
