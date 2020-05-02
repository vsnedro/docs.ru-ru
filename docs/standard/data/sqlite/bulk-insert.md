---
title: Массовая вставка
ms.date: 12/13/2019
description: Рекомендации по повышению производительности, которыми можно воспользоваться при внесении большого количества изменений в базу данных.
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450300"
---
# <a name="bulk-insert"></a><span data-ttu-id="4dbac-103">Массовая вставка</span><span class="sxs-lookup"><span data-stu-id="4dbac-103">Bulk insert</span></span>

<span data-ttu-id="4dbac-104">В SQLite нет специального способа выполнения операций массовой вставки данных.</span><span class="sxs-lookup"><span data-stu-id="4dbac-104">SQLite doesn't have any special way to bulk insert data.</span></span> <span data-ttu-id="4dbac-105">Чтобы обеспечить оптимальную производительность при вставке или обновлении данных, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="4dbac-105">To get optimal performance when inserting or updating data, ensure that you do the following:</span></span>

- <span data-ttu-id="4dbac-106">Использовать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="4dbac-106">Use a transaction.</span></span>
- <span data-ttu-id="4dbac-107">Повторно использовать одну и ту же параметризованную команду.</span><span class="sxs-lookup"><span data-stu-id="4dbac-107">Reuse the same parameterized command.</span></span> <span data-ttu-id="4dbac-108">При последующих выполнениях повторно использовать компиляцию первого выполнения.</span><span class="sxs-lookup"><span data-stu-id="4dbac-108">Subsequent executions will reuse the compilation of the first one.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
