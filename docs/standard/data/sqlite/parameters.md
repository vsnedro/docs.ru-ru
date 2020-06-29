---
title: Параметры
ms.date: 12/13/2019
description: Узнайте, как используются параметры SQL.
ms.openlocfilehash: b24610a5cb65e2b24171452acef9bf55b4995431
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768954"
---
# <a name="parameters"></a><span data-ttu-id="ed463-103">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed463-103">Parameters</span></span>

<span data-ttu-id="ed463-104">Параметры используются для защиты от атак путем внедрения кода SQL.</span><span class="sxs-lookup"><span data-stu-id="ed463-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="ed463-105">Вместо сцепления вводимых пользователем данных с инструкциями SQL используйте параметры, чтобы входные данные всегда воспринимались как литеральное значение и никогда не выполнялись.</span><span class="sxs-lookup"><span data-stu-id="ed463-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="ed463-106">В SQLite параметры обычно разрешены в везде, где допускается использование литерала в инструкциях SQL.</span><span class="sxs-lookup"><span data-stu-id="ed463-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="ed463-107">С параметрами можно использовать префикс `:`, `@` или `$`.</span><span class="sxs-lookup"><span data-stu-id="ed463-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="ed463-108">Сведения о том, как значения .NET сопоставляются со значениями SQLite, см. в разделе [Типы данных](types.md).</span><span class="sxs-lookup"><span data-stu-id="ed463-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="ed463-109">Усечение</span><span class="sxs-lookup"><span data-stu-id="ed463-109">Truncation</span></span>

<span data-ttu-id="ed463-110">Свойство <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> используется для усечения значений типа TEXT и BLOB.</span><span class="sxs-lookup"><span data-stu-id="ed463-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Size = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="ed463-111">Альтернативные типы</span><span class="sxs-lookup"><span data-stu-id="ed463-111">Alternative types</span></span>

<span data-ttu-id="ed463-112">Иногда вам может потребоваться использовать альтернативный тип SQLite.</span><span class="sxs-lookup"><span data-stu-id="ed463-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="ed463-113">Это можно сделать, установив свойство <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>.</span><span class="sxs-lookup"><span data-stu-id="ed463-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="ed463-114">Можно использовать следующие сопоставления альтернативных типов.</span><span class="sxs-lookup"><span data-stu-id="ed463-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="ed463-115">Сопоставления по умолчанию см. в разделе [Типы данных](types.md).</span><span class="sxs-lookup"><span data-stu-id="ed463-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="ed463-116">Значение</span><span class="sxs-lookup"><span data-stu-id="ed463-116">Value</span></span>          | <span data-ttu-id="ed463-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="ed463-117">SqliteType</span></span> | <span data-ttu-id="ed463-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed463-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="ed463-119">Char</span><span class="sxs-lookup"><span data-stu-id="ed463-119">Char</span></span>           | <span data-ttu-id="ed463-120">Целое число</span><span class="sxs-lookup"><span data-stu-id="ed463-120">Integer</span></span>    | <span data-ttu-id="ed463-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="ed463-121">UTF-16</span></span>           |
| <span data-ttu-id="ed463-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="ed463-122">DateTime</span></span>       | <span data-ttu-id="ed463-123">Real</span><span class="sxs-lookup"><span data-stu-id="ed463-123">Real</span></span>       | <span data-ttu-id="ed463-124">Значение дня по юлианскому календарю</span><span class="sxs-lookup"><span data-stu-id="ed463-124">Julian day value</span></span> |
| <span data-ttu-id="ed463-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="ed463-125">DateTimeOffset</span></span> | <span data-ttu-id="ed463-126">Real</span><span class="sxs-lookup"><span data-stu-id="ed463-126">Real</span></span>       | <span data-ttu-id="ed463-127">Значение дня по юлианскому календарю</span><span class="sxs-lookup"><span data-stu-id="ed463-127">Julian day value</span></span> |
| <span data-ttu-id="ed463-128">Guid</span><span class="sxs-lookup"><span data-stu-id="ed463-128">Guid</span></span>           | <span data-ttu-id="ed463-129">Blob</span><span class="sxs-lookup"><span data-stu-id="ed463-129">Blob</span></span>       |                  |
| <span data-ttu-id="ed463-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="ed463-130">TimeSpan</span></span>       | <span data-ttu-id="ed463-131">Real</span><span class="sxs-lookup"><span data-stu-id="ed463-131">Real</span></span>       | <span data-ttu-id="ed463-132">В днях</span><span class="sxs-lookup"><span data-stu-id="ed463-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="ed463-133">Параметры вывода</span><span class="sxs-lookup"><span data-stu-id="ed463-133">Output parameters</span></span>

<span data-ttu-id="ed463-134">SQLite не поддерживает выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="ed463-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="ed463-135">Вместо этого используются возвращаемые значения в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="ed463-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed463-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ed463-136">See also</span></span>

* [<span data-ttu-id="ed463-137">Типы данных</span><span class="sxs-lookup"><span data-stu-id="ed463-137">Data types</span></span>](types.md)
