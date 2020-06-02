---
title: Объединение подключений в пул
description: Узнайте о том, как использовать пулы подключений, способ оптимизации, который ADO.NET использует для снижения затрат на открытие подключений к источникам данных.
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: b8f89dfda7edbde14dbb5945f10f2284ac43c3d8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287094"
---
# <a name="connection-pooling"></a>Объединение подключений в пул
На соединение с источником данных может требоваться значительное время. Для снижения затрат на открытие подключений ADO.NET использует методику оптимизации, называемую *объединением соединений*, что сокращает затраты на многократное открытие и закрытие подключений. Пулы соединений обрабатываются для поставщиков данных .NET Framework по-разному.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Объединение подключений в пул в SQL Server (ADO.NET)](sql-server-connection-pooling.md)  
 Содержит общие сведения о группировании соединений и описание работы пула подключений в SQL Server.  
  
 [OLE DB, ODBC и объединение подключений в пул в Oracle](ole-db-odbc-and-oracle-connection-pooling.md)  
 Описание пулов соединений для поставщика данных .NET Framework для OLE DB, поставщика данных .NET Framework для ODBC и поставщика данных .NET Framework для Oracle.  
  
## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
