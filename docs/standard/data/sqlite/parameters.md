---
title: Параметры
ms.date: 12/13/2019
description: Узнайте, как используются параметры SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401205"
---
# <a name="parameters"></a><span data-ttu-id="44891-103">Параметры</span><span class="sxs-lookup"><span data-stu-id="44891-103">Parameters</span></span>

<span data-ttu-id="44891-104">Параметры используются для защиты от атак путем внедрения кода SQL.</span><span class="sxs-lookup"><span data-stu-id="44891-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="44891-105">Вместо сцепления вводимых пользователем данных с инструкциями SQL используйте параметры, чтобы входные данные всегда воспринимались как литеральное значение и никогда не выполнялись.</span><span class="sxs-lookup"><span data-stu-id="44891-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="44891-106">В SQLite параметры обычно разрешены в везде, где допускается использование литерала в инструкциях SQL.</span><span class="sxs-lookup"><span data-stu-id="44891-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="44891-107">С параметрами можно использовать префикс `:`, `@` или `$`.</span><span class="sxs-lookup"><span data-stu-id="44891-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="44891-108">Сведения о том, как значения .NET сопоставляются со значениями SQLite, см. в разделе [Типы данных](types.md).</span><span class="sxs-lookup"><span data-stu-id="44891-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="44891-109">Усечение</span><span class="sxs-lookup"><span data-stu-id="44891-109">Truncation</span></span>

<span data-ttu-id="44891-110">Свойство <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> используется для усечения значений типа TEXT и BLOB.</span><span class="sxs-lookup"><span data-stu-id="44891-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="44891-111">Альтернативные типы</span><span class="sxs-lookup"><span data-stu-id="44891-111">Alternative types</span></span>

<span data-ttu-id="44891-112">Иногда вам может потребоваться использовать альтернативный тип SQLite.</span><span class="sxs-lookup"><span data-stu-id="44891-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="44891-113">Это можно сделать, установив свойство <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>.</span><span class="sxs-lookup"><span data-stu-id="44891-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="44891-114">Можно использовать следующие сопоставления альтернативных типов.</span><span class="sxs-lookup"><span data-stu-id="44891-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="44891-115">Сопоставления по умолчанию см. в разделе [Типы данных](types.md).</span><span class="sxs-lookup"><span data-stu-id="44891-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="44891-116">Значение</span><span class="sxs-lookup"><span data-stu-id="44891-116">Value</span></span>          | <span data-ttu-id="44891-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="44891-117">SqliteType</span></span> | <span data-ttu-id="44891-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="44891-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="44891-119">Char</span><span class="sxs-lookup"><span data-stu-id="44891-119">Char</span></span>           | <span data-ttu-id="44891-120">Целое число</span><span class="sxs-lookup"><span data-stu-id="44891-120">Integer</span></span>    | <span data-ttu-id="44891-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="44891-121">UTF-16</span></span>           |
| <span data-ttu-id="44891-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="44891-122">DateTime</span></span>       | <span data-ttu-id="44891-123">Real</span><span class="sxs-lookup"><span data-stu-id="44891-123">Real</span></span>       | <span data-ttu-id="44891-124">Значение дня по юлианскому календарю</span><span class="sxs-lookup"><span data-stu-id="44891-124">Julian day value</span></span> |
| <span data-ttu-id="44891-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="44891-125">DateTimeOffset</span></span> | <span data-ttu-id="44891-126">Real</span><span class="sxs-lookup"><span data-stu-id="44891-126">Real</span></span>       | <span data-ttu-id="44891-127">Значение дня по юлианскому календарю</span><span class="sxs-lookup"><span data-stu-id="44891-127">Julian day value</span></span> |
| <span data-ttu-id="44891-128">Guid</span><span class="sxs-lookup"><span data-stu-id="44891-128">Guid</span></span>           | <span data-ttu-id="44891-129">Blob</span><span class="sxs-lookup"><span data-stu-id="44891-129">Blob</span></span>       |                  |
| <span data-ttu-id="44891-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="44891-130">TimeSpan</span></span>       | <span data-ttu-id="44891-131">Real</span><span class="sxs-lookup"><span data-stu-id="44891-131">Real</span></span>       | <span data-ttu-id="44891-132">В днях</span><span class="sxs-lookup"><span data-stu-id="44891-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="44891-133">Параметры вывода</span><span class="sxs-lookup"><span data-stu-id="44891-133">Output parameters</span></span>

<span data-ttu-id="44891-134">SQLite не поддерживает выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="44891-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="44891-135">Вместо этого используются возвращаемые значения в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="44891-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="44891-136">См. также</span><span class="sxs-lookup"><span data-stu-id="44891-136">See also</span></span>

* [<span data-ttu-id="44891-137">Типы данных</span><span class="sxs-lookup"><span data-stu-id="44891-137">Data types</span></span>](types.md)
