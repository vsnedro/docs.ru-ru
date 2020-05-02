---
title: Базы данных в памяти
ms.date: 12/13/2019
description: Узнайте, как использовать базы данных SQLite, выполняющиеся в памяти.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391212"
---
# <a name="in-memory-databases"></a><span data-ttu-id="8699f-103">Базы данных в памяти</span><span class="sxs-lookup"><span data-stu-id="8699f-103">In-memory databases</span></span>

<span data-ttu-id="8699f-104">Выполняющиеся в памяти базы данных SQLite — это базы данных, которые полностью хранятся в памяти, а не на диске.</span><span class="sxs-lookup"><span data-stu-id="8699f-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="8699f-105">Для создания выполняющейся в памяти базы данных используется специальное имя файла источника данных `:memory:`.</span><span class="sxs-lookup"><span data-stu-id="8699f-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="8699f-106">Когда подключение закрывается, база данных удаляется.</span><span class="sxs-lookup"><span data-stu-id="8699f-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="8699f-107">При использовании `:memory:` каждое подключение создает собственную базу данных.</span><span class="sxs-lookup"><span data-stu-id="8699f-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="8699f-108">Общий доступ к выполняющимся в памяти базам данных</span><span class="sxs-lookup"><span data-stu-id="8699f-108">Shareable in-memory databases</span></span>

<span data-ttu-id="8699f-109">Выполняющиеся в памяти базы данных могут совместно использоваться несколькими подключениями, если указать `Mode=Memory` и `Cache=Shared` в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="8699f-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="8699f-110">С помощью ключевого слова `Data Source` можно задать имя для выполняющейся в памяти базы данных.</span><span class="sxs-lookup"><span data-stu-id="8699f-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="8699f-111">Строки подключения, в которых указано одно и то же имя, будут обращаться к одной и той же выполняющейся в памяти базе данных.</span><span class="sxs-lookup"><span data-stu-id="8699f-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="8699f-112">База данных существует, пока остается открытым хотя бы одно подключение к ней.</span><span class="sxs-lookup"><span data-stu-id="8699f-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="8699f-113">На GitHub имеется [пример](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs), который это демонстрирует.</span><span class="sxs-lookup"><span data-stu-id="8699f-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
