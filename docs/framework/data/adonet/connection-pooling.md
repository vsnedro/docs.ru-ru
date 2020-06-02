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
# <a name="connection-pooling"></a><span data-ttu-id="25f99-103">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="25f99-103">Connection Pooling</span></span>
<span data-ttu-id="25f99-104">На соединение с источником данных может требоваться значительное время.</span><span class="sxs-lookup"><span data-stu-id="25f99-104">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="25f99-105">Для снижения затрат на открытие подключений ADO.NET использует методику оптимизации, называемую *объединением соединений*, что сокращает затраты на многократное открытие и закрытие подключений.</span><span class="sxs-lookup"><span data-stu-id="25f99-105">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="25f99-106">Пулы соединений обрабатываются для поставщиков данных .NET Framework по-разному.</span><span class="sxs-lookup"><span data-stu-id="25f99-106">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25f99-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="25f99-107">In This Section</span></span>  
 [<span data-ttu-id="25f99-108">Объединение подключений в пул в SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="25f99-108">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="25f99-109">Содержит общие сведения о группировании соединений и описание работы пула подключений в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25f99-109">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="25f99-110">OLE DB, ODBC и объединение подключений в пул в Oracle</span><span class="sxs-lookup"><span data-stu-id="25f99-110">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="25f99-111">Описание пулов соединений для поставщика данных .NET Framework для OLE DB, поставщика данных .NET Framework для ODBC и поставщика данных .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="25f99-111">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f99-112">См. также</span><span class="sxs-lookup"><span data-stu-id="25f99-112">See also</span></span>

- [<span data-ttu-id="25f99-113">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="25f99-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="25f99-114">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="25f99-114">ADO.NET Overview</span></span>](ado-net-overview.md)
