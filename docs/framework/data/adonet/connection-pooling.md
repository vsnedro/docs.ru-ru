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
# <a name="connection-pooling"></a><span data-ttu-id="435c7-103">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="435c7-103">Connection Pooling</span></span>

<span data-ttu-id="435c7-104">На соединение с источником данных может требоваться значительное время.</span><span class="sxs-lookup"><span data-stu-id="435c7-104">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="435c7-105">Для снижения затрат на открытие подключений ADO.NET использует методику оптимизации, называемую *объединением соединений*, что сокращает затраты на многократное открытие и закрытие подключений.</span><span class="sxs-lookup"><span data-stu-id="435c7-105">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="435c7-106">Пулы соединений обрабатываются для поставщиков данных .NET Framework по-разному.</span><span class="sxs-lookup"><span data-stu-id="435c7-106">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="435c7-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="435c7-107">In This Section</span></span>  

 [<span data-ttu-id="435c7-108">Объединение подключений в пул в SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="435c7-108">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="435c7-109">Содержит общие сведения о группировании соединений и описание работы пула подключений в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="435c7-109">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="435c7-110">OLE DB, ODBC и объединение подключений в пул в Oracle</span><span class="sxs-lookup"><span data-stu-id="435c7-110">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="435c7-111">Описание пулов соединений для поставщика данных .NET Framework для OLE DB, поставщика данных .NET Framework для ODBC и поставщика данных .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="435c7-111">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="435c7-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="435c7-112">See also</span></span>

- [<span data-ttu-id="435c7-113">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="435c7-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="435c7-114">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="435c7-114">ADO.NET Overview</span></span>](ado-net-overview.md)
