---
title: Объединение подключений в пул
description: Узнайте о том, как использовать пулы подключений, способ оптимизации, который ADO.NET использует для снижения затрат на открытие подключений к источникам данных.
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: f16b3ba733cce4a1efe72e3f4eee48a431a96fb7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198721"
---
# <a name="connection-pooling"></a>Объединение подключений в пул

На соединение с источником данных может требоваться значительное время. Для снижения затрат на открытие подключений ADO.NET использует методику оптимизации, называемую *объединением соединений*, что сокращает затраты на многократное открытие и закрытие подключений. Пулы соединений обрабатываются для поставщиков данных .NET Framework по-разному.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Объединение подключений в пул в SQL Server (ADO.NET)](sql-server-connection-pooling.md)  
 Содержит общие сведения о группировании соединений и описание работы пула подключений в SQL Server.  
  
 [OLE DB, ODBC и объединение подключений в пул в Oracle](ole-db-odbc-and-oracle-connection-pooling.md)  
 Описание пулов соединений для поставщика данных .NET Framework для OLE DB, поставщика данных .NET Framework для ODBC и поставщика данных .NET Framework для Oracle.  
  
## <a name="see-also"></a>См. также раздел

- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
