---
title: Двоичные данные и данные большого объема SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: a9296e83b0f4e4352423470433670bb2cbe5a248
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183043"
---
# <a name="sql-server-binary-and-large-value-data"></a>Двоичные данные и данные большого объема SQL Server

SQL Server предоставляет описатель `max`, который расширяет возможности хранения для типов данных `varchar`, `nvarchar` и `varbinary`. Типы данных `varchar(max)`, `nvarchar(max)` и `varbinary(max)` называются *типами данных большого размера*. Можно использовать типы данных больших значений для хранения 2^31–1 байт данных.  
  
 В SQL Server 2008 добавлен элемент FILESTREAM. Это не тип данных, а определяемый на уровне столбца атрибут, позволяющий хранить данные большого размера в файловой системе, а не в базе данных.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Изменение данных больших значений (max) в ADO.NET](modifying-large-value-max-data.md)  
 Описание работы с типами данных больших значений.  
  
 [Данные FILESTREAM](filestream-data.md)  
 Описывает, как работать в SQL Server 2008 с данными большого объема, для которых указан атрибут FILESTREAM.  
  
## <a name="see-also"></a>См. также раздел

- [Типы данных SQL Server и ADO.NET](sql-server-data-types.md)
- [SQL Serverные операции с данными в ADO.NET](sql-server-data-operations.md)
- [Извлечение и изменение данных в ADO.NET](../retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
