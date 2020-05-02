---
title: Ограничения асинхронного режима
ms.date: 12/13/2019
description: Описывает ограничения асинхронных API и некоторых альтернатив, которые можно использовать вместо них.
ms.openlocfilehash: 350237dc5c03023f60e9680e8b9c94aabb62606f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450336"
---
# <a name="async-limitations"></a><span data-ttu-id="623e6-103">Ограничения асинхронного режима</span><span class="sxs-lookup"><span data-stu-id="623e6-103">Async limitations</span></span>

<span data-ttu-id="623e6-104">SQLite не поддерживает асинхронный ввод-вывод.</span><span class="sxs-lookup"><span data-stu-id="623e6-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="623e6-105">Асинхронные методы ADO.NET будут выполняться синхронно в Microsoft.Data.Sqlite.</span><span class="sxs-lookup"><span data-stu-id="623e6-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="623e6-106">Старайтесь не вызывать их.</span><span class="sxs-lookup"><span data-stu-id="623e6-106">Avoid calling them.</span></span>

<span data-ttu-id="623e6-107">Вместо этого используйте [упреждающее протоколирование](https://www.sqlite.org/wal.html) для повышения производительности и параллелизма.</span><span class="sxs-lookup"><span data-stu-id="623e6-107">Instead, use [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="623e6-108">Упреждающее протоколирование включено по умолчанию для баз данных, созданных с помощью [Entity Framework Core](/ef/core/).</span><span class="sxs-lookup"><span data-stu-id="623e6-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
