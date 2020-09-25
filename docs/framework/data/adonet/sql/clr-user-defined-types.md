---
title: Определяемые пользователем типы данных CLR
ms.date: 03/30/2017
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
ms.openlocfilehash: 84d588e0c415daa7de19ea695c817f3eb24f732f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173592"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="f55e9-102">Определяемые пользователем типы данных CLR</span><span class="sxs-lookup"><span data-stu-id="f55e9-102">CLR User-Defined Types</span></span>

<span data-ttu-id="f55e9-103">Microsoft SQL Server предоставляет поддержку определяемых пользователем типов данных (UDT), реализованную при помощи среды CLR в Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f55e9-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="f55e9-104">Среда CLR встроена в SQL Server. Этот механизм позволяет расширять систему типов базы данных.</span><span class="sxs-lookup"><span data-stu-id="f55e9-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="f55e9-105">Определяемые пользователем типы дают возможность расширять систему типов данных SQL Server, а также позволяют определять сложные структурированные типы.</span><span class="sxs-lookup"><span data-stu-id="f55e9-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="f55e9-106">Для архитектуры приложений использование определяемых пользователем типов имеет два основных преимущества.</span><span class="sxs-lookup"><span data-stu-id="f55e9-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
- <span data-ttu-id="f55e9-107">Строгая инкапсуляция (и на клиенте, и на сервере) между внутренним состоянием и внешней функциональностью.</span><span class="sxs-lookup"><span data-stu-id="f55e9-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
- <span data-ttu-id="f55e9-108">Тесная интеграция между другими связанными возможностями сервера.</span><span class="sxs-lookup"><span data-stu-id="f55e9-108">Deep integration with other related server features.</span></span> <span data-ttu-id="f55e9-109">После определения собственного типа данных его можно использовать во всех контекстах, где в SQL Server можно использовать системные типы, включая определения столбцов, а также в качестве переменных, параметров, результатов функций, курсоров, триггеров и репликации.</span><span class="sxs-lookup"><span data-stu-id="f55e9-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="f55e9-110">Дополнительные сведения см. в документации по [SQL Server](/sql) версии SQL Server, которую вы используете.</span><span class="sxs-lookup"><span data-stu-id="f55e9-110">For more detailed information, see the [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="f55e9-111">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f55e9-111">**SQL Server documentation**</span></span>
  
1. [<span data-ttu-id="f55e9-112">Определяемые пользователем типы CLR</span><span class="sxs-lookup"><span data-stu-id="f55e9-112">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="see-also"></a><span data-ttu-id="f55e9-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f55e9-113">See also</span></span>

- [<span data-ttu-id="f55e9-114">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f55e9-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
