---
title: Взаимодействие
ms.date: 12/13/2019
description: Узнайте, как взаимодействовать с библиотеками SQLite.
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450462"
---
# <a name="interoperability"></a><span data-ttu-id="83481-103">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="83481-103">Interoperability</span></span>

<span data-ttu-id="83481-104">Microsoft.Data.Sqlite использует SQLitePCLRaw для взаимодействия с собственной библиотекой SQLite.</span><span class="sxs-lookup"><span data-stu-id="83481-104">Microsoft.Data.Sqlite uses SQLitePCLRaw to interact with the native SQLite library.</span></span> <span data-ttu-id="83481-105">SQLitePCLRaw предоставляет тонкий API .NET через собственный API SQLite.</span><span class="sxs-lookup"><span data-stu-id="83481-105">SQLitePCLRaw provides a thin .NET API over the native SQLite API.</span></span> <span data-ttu-id="83481-106">SqliteConnection и SqliteDataReader предоставляют доступ к базовым объектам SQLitePCLRaw, что позволяет вам напрямую вызывать эти API.</span><span class="sxs-lookup"><span data-stu-id="83481-106">SqliteConnection and SqliteDataReader provide access to the underlying SQLitePCLRaw objects letting you call these APIs directly.</span></span>

<span data-ttu-id="83481-107">В следующем примере показано, как вызвать `sqlite3_trace` для записи выполненных инструкций SQL на консоль:</span><span class="sxs-lookup"><span data-stu-id="83481-107">The following example shows how to call `sqlite3_trace` to write executed SQL statements to the console:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

<span data-ttu-id="83481-108">А в следующем примере показан вызов `sqlite3_stmt_status`, чтобы увидеть, сколько шагов виртуальной машины SQLite скомпилировано в инструкции SQL:</span><span class="sxs-lookup"><span data-stu-id="83481-108">And the following example shows calling `sqlite3_stmt_status` to see how many SQLite virtual machine steps a SQL statement compiled into:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

<span data-ttu-id="83481-109">Объекты SQLitePCLRaw даже предоставляют указатель на собственные объекты, что позволяет вам выполнять P/Invoke для дополнительных собственных API SQLite.</span><span class="sxs-lookup"><span data-stu-id="83481-109">The SQLitePCLRaw objects even expose a pointer to the native objects letting you P/Invoke additional native SQLite APIs.</span></span>
