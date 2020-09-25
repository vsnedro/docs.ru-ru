---
title: Интеграция среды CLR и SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: d9fe0f03c88584607c6bc38fcbcff3f9424fd40c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183030"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="eed5b-102">Интеграция среды CLR и SQL Server</span><span class="sxs-lookup"><span data-stu-id="eed5b-102">SQL Server Common Language Runtime Integration</span></span>

<span data-ttu-id="eed5b-103">В версии SQL Server 2005 появилась поддержка интеграции сервера со средой CLR инфраструктуры .NET Framework для Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="eed5b-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="eed5b-104">Это означает, что хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции, определяемые пользователем агрегатные функции и возвращающие табличные значение потоковые функции теперь можно разрабатывать с использованием любого языка .NET Framework, включая Microsoft Visual Basic .NET и Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="eed5b-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="eed5b-105">Пространство имен <xref:Microsoft.SqlServer.Server> содержит ряд новых API-интерфейсов, что позволяет обеспечить взаимодействие управляемого кода со средой Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eed5b-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="eed5b-106">В настоящем разделе приведено описание средств и особенностей функционирования, которые появляются в результате интеграции SQL Server со средой CLR, а также внутрипроцессные модули SQL Server, предназначенные для поддержки технологии ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="eed5b-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="eed5b-107">Этот раздел предназначен для предоставления лишь такого количества сведений, с которого можно приступать к программированию в рамках интеграции SQL Server со средой CLR, и не рассчитан на всестороннее изложение.</span><span class="sxs-lookup"><span data-stu-id="eed5b-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="eed5b-108">Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eed5b-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="eed5b-109">**Документация по SQL Server**</span><span class="sxs-lookup"><span data-stu-id="eed5b-109">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="eed5b-110">Основные понятия о программировании интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="eed5b-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts)  
  
## <a name="in-this-section"></a><span data-ttu-id="eed5b-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="eed5b-111">In This Section</span></span>  

 [<span data-ttu-id="eed5b-112">Знакомство с интеграцией CLR в SQL Server</span><span class="sxs-lookup"><span data-stu-id="eed5b-112">Introduction to SQL Server CLR Integration</span></span>](introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="eed5b-113">Предоставляет вводные сведения об интеграции SQL Server со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="eed5b-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="eed5b-114">Приводятся ссылки на дополнительные разделы.</span><span class="sxs-lookup"><span data-stu-id="eed5b-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="eed5b-115">Определяемые пользователем функции среды CLR</span><span class="sxs-lookup"><span data-stu-id="eed5b-115">CLR User-Defined Functions</span></span>](clr-user-defined-functions.md)  
 <span data-ttu-id="eed5b-116">Описывает реализацию и использование различных типов функций CLR: возвращающих табличное значение, скалярных и определяемых пользователем агрегатных функций.</span><span class="sxs-lookup"><span data-stu-id="eed5b-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="eed5b-117">Определяемые пользователем типы CLR</span><span class="sxs-lookup"><span data-stu-id="eed5b-117">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
 <span data-ttu-id="eed5b-118">Показывает, как реализовать и использовать определяемые пользователем типы данных CLR.</span><span class="sxs-lookup"><span data-stu-id="eed5b-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="eed5b-119">Приводятся ссылки на дополнительные разделы.</span><span class="sxs-lookup"><span data-stu-id="eed5b-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="eed5b-120">Хранимые процедуры CLR</span><span class="sxs-lookup"><span data-stu-id="eed5b-120">CLR Stored Procedures</span></span>](clr-stored-procedures.md)  
 <span data-ttu-id="eed5b-121">Показывает, как реализовать и использовать хранимые процедуры CLR.</span><span class="sxs-lookup"><span data-stu-id="eed5b-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="eed5b-122">Приводятся ссылки на дополнительные разделы.</span><span class="sxs-lookup"><span data-stu-id="eed5b-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="eed5b-123">Триггеры CLR</span><span class="sxs-lookup"><span data-stu-id="eed5b-123">CLR Triggers</span></span>](clr-triggers.md)  
 <span data-ttu-id="eed5b-124">Показывает, как реализовать и использовать триггеры CLR.</span><span class="sxs-lookup"><span data-stu-id="eed5b-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="eed5b-125">Приводятся ссылки на дополнительные разделы.</span><span class="sxs-lookup"><span data-stu-id="eed5b-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="eed5b-126">Контекстное соединение</span><span class="sxs-lookup"><span data-stu-id="eed5b-126">The Context Connection</span></span>](the-context-connection.md)  
 <span data-ttu-id="eed5b-127">Сведения о контекстном подключении.</span><span class="sxs-lookup"><span data-stu-id="eed5b-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="eed5b-128">Внутрипроцессное поведение ADO.NET в SQL Server</span><span class="sxs-lookup"><span data-stu-id="eed5b-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="eed5b-129">Описывает внутрипроцессные модули SQL Server, предназначенные для поддержки технологии ADO.NET, и контекстное соединение.</span><span class="sxs-lookup"><span data-stu-id="eed5b-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="eed5b-130">Приводятся ссылки на дополнительные разделы.</span><span class="sxs-lookup"><span data-stu-id="eed5b-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eed5b-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eed5b-131">See also</span></span>

- [<span data-ttu-id="eed5b-132">SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eed5b-132">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="eed5b-133">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eed5b-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
