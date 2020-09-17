---
title: Ограничения асинхронного режима
ms.date: 09/04/2020
description: Описывает ограничения асинхронных API и некоторых альтернатив, которые можно использовать вместо них.
ms.openlocfilehash: 8b14fcfeb12d331d8d43ca6d77332007a12ae5dc
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515999"
---
# <a name="async-limitations"></a><span data-ttu-id="6e642-103">Ограничения асинхронного режима</span><span class="sxs-lookup"><span data-stu-id="6e642-103">Async limitations</span></span>

<span data-ttu-id="6e642-104">SQLite не поддерживает асинхронный ввод-вывод.</span><span class="sxs-lookup"><span data-stu-id="6e642-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="6e642-105">Асинхронные методы ADO.NET будут выполняться синхронно в Microsoft.Data.Sqlite.</span><span class="sxs-lookup"><span data-stu-id="6e642-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="6e642-106">Старайтесь не вызывать их.</span><span class="sxs-lookup"><span data-stu-id="6e642-106">Avoid calling them.</span></span>

<span data-ttu-id="6e642-107">Вместо этого используйте [общий кэш](connection-strings.md#cache) и [упреждающее протоколирование](https://www.sqlite.org/wal.html) для повышения производительности и параллелизма.</span><span class="sxs-lookup"><span data-stu-id="6e642-107">Instead, use a [shared cache](connection-strings.md#cache) and [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="6e642-108">Упреждающее протоколирование включено по умолчанию для баз данных, созданных с помощью [Entity Framework Core](/ef/core/).</span><span class="sxs-lookup"><span data-stu-id="6e642-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
