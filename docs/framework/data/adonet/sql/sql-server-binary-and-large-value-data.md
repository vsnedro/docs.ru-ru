---
description: 'Дополнительные сведения: SQL Server двоичные данные и Large-Value данных'
title: Двоичные данные и данные большого объема SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 8c7da5d504af0bc1beeea7e210a6fff4157fb090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767444"
---
# <a name="sql-server-binary-and-large-value-data"></a>Двоичные данные и данные большого объема SQL Server

SQL Server предоставляет описатель `max`, который расширяет возможности хранения для типов данных `varchar`, `nvarchar` и `varbinary`. Типы данных `varchar(max)`, `nvarchar(max)` и `varbinary(max)` называются *типами данных большого размера*. Можно использовать типы данных больших значений для хранения 2^31–1 байт данных.  
  
 В SQL Server 2008 добавлен элемент FILESTREAM. Это не тип данных, а определяемый на уровне столбца атрибут, позволяющий хранить данные большого размера в файловой системе, а не в базе данных.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Изменение данных Large-Value (max) в ADO.NET](modifying-large-value-max-data.md)  
 Описание работы с типами данных больших значений.  
  
 [Данные FILESTREAM](filestream-data.md)  
 Описывает, как работать в SQL Server 2008 с данными большого объема, для которых указан атрибут FILESTREAM.  
  
## <a name="see-also"></a>См. также

- [Типы данных SQL Server и ADO.NET](sql-server-data-types.md)
- [SQL Serverные операции с данными в ADO.NET](sql-server-data-operations.md)
- [Извлечение и изменение данных в ADO.NET](../retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
