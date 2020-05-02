---
title: Определяемые пользователем функции
ms.date: 12/13/2019
description: Узнайте, как создавать определяемые пользователем скалярные и агрегатные функции.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450414"
---
# <a name="user-defined-functions"></a><span data-ttu-id="eea3f-103">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="eea3f-103">User-defined functions</span></span>

<span data-ttu-id="eea3f-104">Большинство баз данных имеют процедурный диалект SQL, который можно использовать для определения собственных функций.</span><span class="sxs-lookup"><span data-stu-id="eea3f-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="eea3f-105">SQLite, однако, работает в процессе с приложением.</span><span class="sxs-lookup"><span data-stu-id="eea3f-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="eea3f-106">Вместо того чтобы изучать новый диалект SQL, можно просто использовать язык программирования приложения.</span><span class="sxs-lookup"><span data-stu-id="eea3f-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="eea3f-107">Скалярные функции</span><span class="sxs-lookup"><span data-stu-id="eea3f-107">Scalar functions</span></span>

<span data-ttu-id="eea3f-108">Скалярные функции возвращают одно скалярное значение для каждой строки в запросе.</span><span class="sxs-lookup"><span data-stu-id="eea3f-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="eea3f-109">Определяйте новые скалярные функции и переопределяйте встроенные, используя <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span><span class="sxs-lookup"><span data-stu-id="eea3f-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="eea3f-110">Раздел [Типы данных](types.md) содержит список поддерживаемых параметров и возвращаемых типов для аргумента `func`.</span><span class="sxs-lookup"><span data-stu-id="eea3f-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="eea3f-111">При указании аргумента `state` это значение будет передаваться в каждый вызов функции.</span><span class="sxs-lookup"><span data-stu-id="eea3f-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="eea3f-112">Используйте этот способ, чтобы избежать завершений.</span><span class="sxs-lookup"><span data-stu-id="eea3f-112">Use this to avoid closures.</span></span>

<span data-ttu-id="eea3f-113">Укажите `isDeterministic`, если функция является детерминированной, чтобы разрешить SQLite использовать дополнительные оптимизации при компиляции запросов.</span><span class="sxs-lookup"><span data-stu-id="eea3f-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="eea3f-114">В следующем примере показано, как добавить скалярную функцию для вычисления радиуса цилиндра.</span><span class="sxs-lookup"><span data-stu-id="eea3f-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="eea3f-115">Операторы</span><span class="sxs-lookup"><span data-stu-id="eea3f-115">Operators</span></span>

<span data-ttu-id="eea3f-116">Следующие операторы SQLite реализуются соответствующими скалярными функциями.</span><span class="sxs-lookup"><span data-stu-id="eea3f-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="eea3f-117">Определение этих скалярных функций в приложении будет переопределять поведение этих операторов.</span><span class="sxs-lookup"><span data-stu-id="eea3f-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="eea3f-118">Оператор</span><span class="sxs-lookup"><span data-stu-id="eea3f-118">Operator</span></span>          | <span data-ttu-id="eea3f-119">Функция</span><span class="sxs-lookup"><span data-stu-id="eea3f-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="eea3f-120">X GLOB Y</span><span class="sxs-lookup"><span data-stu-id="eea3f-120">X GLOB Y</span></span>          | <span data-ttu-id="eea3f-121">glob(Y, X)</span><span class="sxs-lookup"><span data-stu-id="eea3f-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="eea3f-122">X LIKE Y</span><span class="sxs-lookup"><span data-stu-id="eea3f-122">X LIKE Y</span></span>          | <span data-ttu-id="eea3f-123">like(Y, X)</span><span class="sxs-lookup"><span data-stu-id="eea3f-123">like(Y, X)</span></span>    |
| <span data-ttu-id="eea3f-124">X LIKE Y ESCAPE Z</span><span class="sxs-lookup"><span data-stu-id="eea3f-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="eea3f-125">like(Y, X, Z)</span><span class="sxs-lookup"><span data-stu-id="eea3f-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="eea3f-126">X MATCH Y</span><span class="sxs-lookup"><span data-stu-id="eea3f-126">X MATCH Y</span></span>         | <span data-ttu-id="eea3f-127">match(Y, X)</span><span class="sxs-lookup"><span data-stu-id="eea3f-127">match(Y, X)</span></span>   |
| <span data-ttu-id="eea3f-128">X REGEXP Y</span><span class="sxs-lookup"><span data-stu-id="eea3f-128">X REGEXP Y</span></span>        | <span data-ttu-id="eea3f-129">regexp(Y, X)</span><span class="sxs-lookup"><span data-stu-id="eea3f-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="eea3f-130">В следующем примере показано, как определить функцию regexp для включения соответствующего оператора.</span><span class="sxs-lookup"><span data-stu-id="eea3f-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="eea3f-131">SQLite не включает реализацию по умолчанию функции regexp.</span><span class="sxs-lookup"><span data-stu-id="eea3f-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="eea3f-132">Агрегатные функции</span><span class="sxs-lookup"><span data-stu-id="eea3f-132">Aggregate functions</span></span>

<span data-ttu-id="eea3f-133">Агрегатные функции возвращают одно агрегированное значение для всех строк в запросе.</span><span class="sxs-lookup"><span data-stu-id="eea3f-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="eea3f-134">Определяйте и переопределяйте агрегатные функции с помощью <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span><span class="sxs-lookup"><span data-stu-id="eea3f-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="eea3f-135">Аргумент `seed` указывает начальное состояние контекста.</span><span class="sxs-lookup"><span data-stu-id="eea3f-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="eea3f-136">Он также используется, чтобы избежать завершений.</span><span class="sxs-lookup"><span data-stu-id="eea3f-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="eea3f-137">Аргумент `func` вызывается один раз для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="eea3f-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="eea3f-138">Используйте контекст для накопления конечного результата.</span><span class="sxs-lookup"><span data-stu-id="eea3f-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="eea3f-139">Возвратите контекст.</span><span class="sxs-lookup"><span data-stu-id="eea3f-139">Return the context.</span></span> <span data-ttu-id="eea3f-140">Этот шаблон позволяет контексту быть типом значения или неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="eea3f-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="eea3f-141">Если `resultSelector` не указано, в качестве результата используется конечное состояние контекста.</span><span class="sxs-lookup"><span data-stu-id="eea3f-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="eea3f-142">Это может упростить определение функций, таких как sum и count, для которых требуется только увеличение числа строк и их возврат.</span><span class="sxs-lookup"><span data-stu-id="eea3f-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="eea3f-143">Укажите `resultSelector`, чтобы вычислить окончательный результат из контекста после прохода по всем строкам.</span><span class="sxs-lookup"><span data-stu-id="eea3f-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="eea3f-144">Раздел [Типы данных](types.md) содержит список поддерживаемых параметров для аргумента `func` и возвращаемых типов для `resultSelector`.</span><span class="sxs-lookup"><span data-stu-id="eea3f-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="eea3f-145">Укажите `isDeterministic`, если функция является детерминированной, чтобы разрешить SQLite использовать дополнительные оптимизации при компиляции запросов.</span><span class="sxs-lookup"><span data-stu-id="eea3f-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="eea3f-146">В следующем примере определяется агрегатная функция для вычисления стандартного отклонения столбца.</span><span class="sxs-lookup"><span data-stu-id="eea3f-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="eea3f-147">Ошибки</span><span class="sxs-lookup"><span data-stu-id="eea3f-147">Errors</span></span>

<span data-ttu-id="eea3f-148">Если определяемая пользователем функция создает исключение, сообщение возвращается SQLite.</span><span class="sxs-lookup"><span data-stu-id="eea3f-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="eea3f-149">Затем SQLite вызовет ошибку, а Microsoft.Data.SQLite вызовет SqliteException.</span><span class="sxs-lookup"><span data-stu-id="eea3f-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="eea3f-150">Дополнительные сведения см. в статье [Ошибки базы данных](database-errors.md).</span><span class="sxs-lookup"><span data-stu-id="eea3f-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="eea3f-151">По умолчанию кодом ошибки SQLite будет SQLITE_ERROR (или 1).</span><span class="sxs-lookup"><span data-stu-id="eea3f-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="eea3f-152">Но его можно изменить, выполнив <xref:Microsoft.Data.Sqlite.SqliteException> в функции с указанным нужным <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode>.</span><span class="sxs-lookup"><span data-stu-id="eea3f-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="eea3f-153">Отладка</span><span class="sxs-lookup"><span data-stu-id="eea3f-153">Debugging</span></span>

<span data-ttu-id="eea3f-154">SQLite вызывает вашу реализацию напрямую.</span><span class="sxs-lookup"><span data-stu-id="eea3f-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="eea3f-155">Это позволяет добавлять точки останова, которые инициируются, когда SQLite оценивает запросы.</span><span class="sxs-lookup"><span data-stu-id="eea3f-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="eea3f-156">Для создания определяемых пользователем функций доступны все возможности отладки .NET.</span><span class="sxs-lookup"><span data-stu-id="eea3f-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="eea3f-157">См. также</span><span class="sxs-lookup"><span data-stu-id="eea3f-157">See also</span></span>

* [<span data-ttu-id="eea3f-158">Типы данных</span><span class="sxs-lookup"><span data-stu-id="eea3f-158">Data types</span></span>](types.md)
* [<span data-ttu-id="eea3f-159">Функции ядра SQLite</span><span class="sxs-lookup"><span data-stu-id="eea3f-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="eea3f-160">Агрегатные функции SQLite</span><span class="sxs-lookup"><span data-stu-id="eea3f-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
