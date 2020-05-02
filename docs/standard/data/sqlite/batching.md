---
title: Пакетная обработка
ms.date: 12/13/2019
description: Сведения о том, как выполнить пакет инструкций SQL в одной команде.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450312"
---
# <a name="batching"></a><span data-ttu-id="2011a-103">Пакетная обработка</span><span class="sxs-lookup"><span data-stu-id="2011a-103">Batching</span></span>

<span data-ttu-id="2011a-104">В SQLite нет собственной поддержки пакетной обработки инструкций SQL в одной команде.</span><span class="sxs-lookup"><span data-stu-id="2011a-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="2011a-105">Но так как сеть не используется, это не окажет никакого положительного влияния на производительность.</span><span class="sxs-lookup"><span data-stu-id="2011a-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="2011a-106">Однако Microsoft.Data.Sqlite для удобства реализует пакетную обработку инструкций в качестве удобства, чтобы его поведение было больше похоже на другие поставщики ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2011a-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="2011a-107">При вызове <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType> инструкции выполняются вплоть до первой инструкции, возвращающей результаты.</span><span class="sxs-lookup"><span data-stu-id="2011a-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="2011a-108">При вызове <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> выполнение инструкций продолжается до следующей инструкции, возвращающей результаты, или до конца пакета.</span><span class="sxs-lookup"><span data-stu-id="2011a-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="2011a-109">При вызове <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> или <xref:System.Data.Common.DbDataReader.Close%2A> выполняются все оставшиеся инструкции, которые не были использованы `NextResult()`.</span><span class="sxs-lookup"><span data-stu-id="2011a-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="2011a-110">Если не очистить модуль чтения данных, метод завершения пытается выполнить оставшиеся инструкции, но все возникающие ошибки игнорируются.</span><span class="sxs-lookup"><span data-stu-id="2011a-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="2011a-111">Поэтому при использовании пакетов важно очищать объекты `DbDataReader`.</span><span class="sxs-lookup"><span data-stu-id="2011a-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="2011a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2011a-112">See also</span></span>

* [<span data-ttu-id="2011a-113">Массовая вставка</span><span class="sxs-lookup"><span data-stu-id="2011a-113">Bulk Insert</span></span>](bulk-insert.md)
