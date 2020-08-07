---
title: Форматирование обычного текста
description: 'Узнайте, как использовать printf и другое форматирование в виде обычного текста в приложениях и скриптах F #.'
ms.date: 07/22/2020
ms.openlocfilehash: 6b14633e074961757d0f0cd258d1b1667f5fd8ee
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854923"
---
# <a name="plain-text-formatting"></a><span data-ttu-id="b8305-103">Форматирование обычного текста</span><span class="sxs-lookup"><span data-stu-id="b8305-103">Plain text formatting</span></span>

<span data-ttu-id="b8305-104">F # поддерживает форматирование с проверкой типа на обычный текст с помощью `printf` `printfn` функций,, `sprintf` и.</span><span class="sxs-lookup"><span data-stu-id="b8305-104">F# supports type-checked formatting of plain text using `printf`, `printfn`, `sprintf`, and related functions.</span></span>
<span data-ttu-id="b8305-105">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-105">For example,</span></span>

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

<span data-ttu-id="b8305-106">дает выходные данные</span><span class="sxs-lookup"><span data-stu-id="b8305-106">gives the output</span></span>

```fsharp
Hello world, 2 + 2 is 4
```

<span data-ttu-id="b8305-107">F # также позволяет форматировать структурированные значения в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="b8305-107">F# also allows structured values to be formatted as plain text.</span></span>
<span data-ttu-id="b8305-108">Например, рассмотрим следующий пример, в котором выходные данные форматируются как отображение кортежей в виде матрицы.</span><span class="sxs-lookup"><span data-stu-id="b8305-108">For example, consider the following example that formats the output as a matrix-like display of tuples.</span></span>

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

<span data-ttu-id="b8305-109">Структурированное форматирование обычного текста активируется при использовании `%A` формата в `printf` строках форматирования.</span><span class="sxs-lookup"><span data-stu-id="b8305-109">Structured plain text formatting is activated when you use the `%A` format in `printf` formatting strings.</span></span>
<span data-ttu-id="b8305-110">Он также активируется при форматировании выходных данных значений в F # Interactive, где выходные данные содержат дополнительные сведения, а также являются настраиваемыми.</span><span class="sxs-lookup"><span data-stu-id="b8305-110">It's also activated when formatting the output of values in F# interactive, where the output includes extra information and is additionally customizable.</span></span>
<span data-ttu-id="b8305-111">Форматирование в виде обычного текста также наблюдаемое через вызовы в `x.ToString()` отношении объединения и записи F #, включая те, которые происходят неявно при отладке, ведении журнала и других средствах.</span><span class="sxs-lookup"><span data-stu-id="b8305-111">Plain text formatting is also observable through any calls to `x.ToString()` on F# union and record values, including those that occur implicitly in debugging, logging, and other tooling.</span></span>

## <a name="checking-of-printf-format-strings"></a><span data-ttu-id="b8305-112">Проверка `printf` строк формата</span><span class="sxs-lookup"><span data-stu-id="b8305-112">Checking of `printf`-format strings</span></span>

<span data-ttu-id="b8305-113">Если `printf` функция форматирования используется с аргументом, который не соответствует спецификаторам формата printf в строке формата, будет выведено сообщение об ошибке времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="b8305-113">A compile-time error will be reported if a `printf` formatting function is used with an argument that doesn't match the printf format specifiers in the format string.</span></span>  <span data-ttu-id="b8305-114">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-114">For example,</span></span>

```fsharp
sprintf "Hello %s" (2+2)
```

<span data-ttu-id="b8305-115">дает выходные данные</span><span class="sxs-lookup"><span data-stu-id="b8305-115">gives the output</span></span>

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

<span data-ttu-id="b8305-116">Технически говоря, при использовании `printf` и других связанных функций специальное правило в компиляторе F # проверяет строковый литерал, переданный в качестве строки формата, гарантируя, что последующие аргументы имеют правильный тип в соответствии с используемыми описателями формата.</span><span class="sxs-lookup"><span data-stu-id="b8305-116">Technically speaking, when using `printf` and other related functions, a special rule in the F# compiler checks the string literal passed as the format string, ensuring the subsequent arguments applied are of the correct type to match the format specifiers used.</span></span>

## <a name="format-specifiers-for-printf"></a><span data-ttu-id="b8305-117">Описатели формата для`printf`</span><span class="sxs-lookup"><span data-stu-id="b8305-117">Format specifiers for `printf`</span></span>

<span data-ttu-id="b8305-118">Спецификации формата для `printf` форматов — это строки с `%` маркерами, которые указывают на формат.</span><span class="sxs-lookup"><span data-stu-id="b8305-118">Format specifications for `printf` formats are strings with `%` markers that indicate format.</span></span> <span data-ttu-id="b8305-119">Заполнители формата состоят из того `%[flags][width][.precision][type]` места, где тип интерпретируется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b8305-119">Format placeholders consist of `%[flags][width][.precision][type]` where the type is interpreted as follows:</span></span>

| <span data-ttu-id="b8305-120">Описатель формата</span><span class="sxs-lookup"><span data-stu-id="b8305-120">Format specifier</span></span>   | <span data-ttu-id="b8305-121">Типы (s)</span><span class="sxs-lookup"><span data-stu-id="b8305-121">Type(s)</span></span>        | <span data-ttu-id="b8305-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="b8305-122">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | <span data-ttu-id="b8305-123">bool</span><span class="sxs-lookup"><span data-stu-id="b8305-123">bool</span></span>      | <span data-ttu-id="b8305-124">В формате `true` или`false`</span><span class="sxs-lookup"><span data-stu-id="b8305-124">Formatted as `true` or `false`</span></span>                |
| `%s`               | <span data-ttu-id="b8305-125">строка</span><span class="sxs-lookup"><span data-stu-id="b8305-125">string</span></span>    | <span data-ttu-id="b8305-126">Отформатировано как Неэкранированное содержимое</span><span class="sxs-lookup"><span data-stu-id="b8305-126">Formatted as its unescaped contents</span></span>         |
| `%c`               | <span data-ttu-id="b8305-127">char</span><span class="sxs-lookup"><span data-stu-id="b8305-127">char</span></span>      | <span data-ttu-id="b8305-128">Отформатировано как символьный литерал</span><span class="sxs-lookup"><span data-stu-id="b8305-128">Formatted as the character literal</span></span>  |
| <span data-ttu-id="b8305-129">`%d`, `%i`</span><span class="sxs-lookup"><span data-stu-id="b8305-129">`%d`, `%i`</span></span>         | <span data-ttu-id="b8305-130">Базовый целочисленный тип</span><span class="sxs-lookup"><span data-stu-id="b8305-130">a basic integer type</span></span> | <span data-ttu-id="b8305-131">Отформатировано как десятичное целое число, подписанное, если базовый целочисленный тип имеет знак</span><span class="sxs-lookup"><span data-stu-id="b8305-131">Formatted as a decimal integer, signed if the basic integer type is signed</span></span> |
| `%u`               | <span data-ttu-id="b8305-132">Базовый целочисленный тип</span><span class="sxs-lookup"><span data-stu-id="b8305-132">a basic integer type</span></span> | <span data-ttu-id="b8305-133">Отформатировано как десятичное целое число без знака</span><span class="sxs-lookup"><span data-stu-id="b8305-133">Formatted as an unsigned decimal integer</span></span>   |
| <span data-ttu-id="b8305-134">`%x`, `%X`</span><span class="sxs-lookup"><span data-stu-id="b8305-134">`%x`, `%X`</span></span>         | <span data-ttu-id="b8305-135">Базовый целочисленный тип</span><span class="sxs-lookup"><span data-stu-id="b8305-135">a basic integer type</span></span> | <span data-ttu-id="b8305-136">Отформатировано как шестнадцатеричное число без знака (a-f или A-F для шестнадцатеричных цифр соответственно)</span><span class="sxs-lookup"><span data-stu-id="b8305-136">Formatted as an unsigned hexadecimal number (a-f or A-F for hex digits respectively)</span></span>  |
|  `%o`              | <span data-ttu-id="b8305-137">Базовый целочисленный тип</span><span class="sxs-lookup"><span data-stu-id="b8305-137">a basic integer type</span></span> | <span data-ttu-id="b8305-138">Отформатировано как восьмеричное число без знака</span><span class="sxs-lookup"><span data-stu-id="b8305-138">Formatted as an unsigned octal number</span></span> |
| <span data-ttu-id="b8305-139">`%e`, `%E`</span><span class="sxs-lookup"><span data-stu-id="b8305-139">`%e`, `%E`</span></span>         | <span data-ttu-id="b8305-140">базовый тип с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="b8305-140">a basic floating point type</span></span> | <span data-ttu-id="b8305-141">В виде значения со знаком, имеющего форму, `[-]d.dddde[sign]ddd` где d — одна десятичная цифра, dddd — одна или несколько десятичных цифр, DDD — ровно три десятичных цифры, а знак — `+` или`-`</span><span class="sxs-lookup"><span data-stu-id="b8305-141">Formatted as a signed value having the form `[-]d.dddde[sign]ddd` where d is a single decimal digit, dddd is one or more decimal digits, ddd is exactly three decimal digits, and sign is `+` or `-`</span></span> |
| `%f`               | <span data-ttu-id="b8305-142">базовый тип с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="b8305-142">a basic floating point type</span></span> | <span data-ttu-id="b8305-143">Отформатировано как значение со знаком, имеющее форму `[-]dddd.dddd` , где `dddd` — одна или несколько десятичных цифр.</span><span class="sxs-lookup"><span data-stu-id="b8305-143">Formatted as a signed value having the form `[-]dddd.dddd`, where `dddd` is one or more decimal digits.</span></span> <span data-ttu-id="b8305-144">Количество цифр перед десятичной запятой зависит от величины числа, а количество знаков после десятичной запятой зависит от указанной точности.</span><span class="sxs-lookup"><span data-stu-id="b8305-144">The number of digits before the decimal point depends on the magnitude of the number, and the number of digits after the decimal point depends on the requested precision.</span></span> |
| <span data-ttu-id="b8305-145">`%g`, `%G`</span><span class="sxs-lookup"><span data-stu-id="b8305-145">`%g`, `%G`</span></span> | <span data-ttu-id="b8305-146">базовый тип с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="b8305-146">a basic floating point type</span></span> |  <span data-ttu-id="b8305-147">Форматировано с использованием в качестве значения, напечатанного в `%f` `%e` формате или, в зависимости от того, какое значение является более компактным для заданного значения и точности.</span><span class="sxs-lookup"><span data-stu-id="b8305-147">Formatted using as a signed value printed in `%f` or `%e` format, whichever is more compact for the given value and precision.</span></span> |
| `%M` | <span data-ttu-id="b8305-148">`System.Decimal`значение</span><span class="sxs-lookup"><span data-stu-id="b8305-148">a `System.Decimal` value</span></span>  |    <span data-ttu-id="b8305-149">Отформатировано с помощью `"G"` описателя формата для`System.Decimal.ToString(format)`</span><span class="sxs-lookup"><span data-stu-id="b8305-149">Formatted using the `"G"` format specifier for `System.Decimal.ToString(format)`</span></span> |
| `%O` | <span data-ttu-id="b8305-150">любое значение</span><span class="sxs-lookup"><span data-stu-id="b8305-150">any value</span></span>  |   <span data-ttu-id="b8305-151">Отформатировано с помощью упаковки-преобразования объекта и вызова его `System.Object.ToString()` метода</span><span class="sxs-lookup"><span data-stu-id="b8305-151">Formatted by boxing the object and calling its `System.Object.ToString()` method</span></span> |
| `%A` | <span data-ttu-id="b8305-152">любое значение</span><span class="sxs-lookup"><span data-stu-id="b8305-152">any value</span></span>  |   <span data-ttu-id="b8305-153">Форматирование с использованием [структурированного форматирования обычного текста](plaintext-formatting.md) с параметрами макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b8305-153">Formatted using [structured plain text formatting](plaintext-formatting.md) with the default layout settings</span></span> |
| `%a` | <span data-ttu-id="b8305-154">любое значение</span><span class="sxs-lookup"><span data-stu-id="b8305-154">any value</span></span>  |   <span data-ttu-id="b8305-155">Требуется два аргумента: функция форматирования, принимающая параметр контекста и значение, и конкретное значение для печати</span><span class="sxs-lookup"><span data-stu-id="b8305-155">Requires two arguments: a formatting function accepting a context parameter and the value, and the particular value to print</span></span> |
| `%t` | <span data-ttu-id="b8305-156">любое значение</span><span class="sxs-lookup"><span data-stu-id="b8305-156">any value</span></span>  |   <span data-ttu-id="b8305-157">Требуется один аргумент: функция форматирования, принимающая параметр контекста, который либо выводит, либо возвращает соответствующий текст.</span><span class="sxs-lookup"><span data-stu-id="b8305-157">Requires one argument: a formatting function accepting a context parameter that either outputs or returns the appropriate text</span></span> |

<span data-ttu-id="b8305-158">Базовые целочисленные типы: `byte` ( `System.Byte` ), `sbyte` ( `System.SByte` ), `int16` ( `System.Int16` ), `uint16` ( `System.UInt16` ), `int32` ( `System.Int32` ), `uint32` ( `System.UInt32` ), `int64` ( `System.Int64` ), `uint64` (), () `System.UInt64` `nativeint` `System.IntPtr` и `unativeint` ( `System.UIntPtr` ).</span><span class="sxs-lookup"><span data-stu-id="b8305-158">Basic integer types are `byte` (`System.Byte`), `sbyte` (`System.SByte`), `int16` (`System.Int16`), `uint16` (`System.UInt16`), `int32` (`System.Int32`), `uint32` (`System.UInt32`), `int64` (`System.Int64`), `uint64` (`System.UInt64`), `nativeint`  (`System.IntPtr`), and `unativeint`  (`System.UIntPtr`).</span></span>
<span data-ttu-id="b8305-159">Базовые типы с плавающей запятой: `float` ( `System.Double` ) и `float32` ( `System.Single` ).</span><span class="sxs-lookup"><span data-stu-id="b8305-159">Basic floating point types are `float` (`System.Double`) and `float32` (`System.Single`).</span></span>

<span data-ttu-id="b8305-160">Необязательная ширина — это целое число, указывающее минимальную ширину результата.</span><span class="sxs-lookup"><span data-stu-id="b8305-160">The optional width is an integer indicating the minimal width of the result.</span></span> <span data-ttu-id="b8305-161">Например, `%6d` выводит целое число, предваряя его пробелами, чтобы заполнить не менее шести символов.</span><span class="sxs-lookup"><span data-stu-id="b8305-161">For instance, `%6d` prints an integer, prefixing it with spaces to fill at least six characters.</span></span> <span data-ttu-id="b8305-162">Если задано значение Width `*` , то для указания соответствующей ширины берется дополнительный целочисленный аргумент.</span><span class="sxs-lookup"><span data-stu-id="b8305-162">If width is `*`, then an extra integer  argument is taken to specify the corresponding width.</span></span>

<span data-ttu-id="b8305-163">Допустимые флаги:</span><span class="sxs-lookup"><span data-stu-id="b8305-163">Valid flags are:</span></span>

| <span data-ttu-id="b8305-164">Flag</span><span class="sxs-lookup"><span data-stu-id="b8305-164">Flag</span></span>   | <span data-ttu-id="b8305-165">Действие</span><span class="sxs-lookup"><span data-stu-id="b8305-165">Effect</span></span>        | <span data-ttu-id="b8305-166">Remarks</span><span class="sxs-lookup"><span data-stu-id="b8305-166">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | <span data-ttu-id="b8305-167">Добавьте нули вместо пробелов, чтобы сделать требуемую ширину</span><span class="sxs-lookup"><span data-stu-id="b8305-167">Add zeros instead of spaces to make up the required width</span></span> |    |
| `-` |  <span data-ttu-id="b8305-168">Выровнять результат по левому краю указанной ширины</span><span class="sxs-lookup"><span data-stu-id="b8305-168">Left justify the result within the specified width</span></span> |   |
| `+`  | <span data-ttu-id="b8305-169">Добавить `+` символ, если число является положительным (для соответствия `-` знаку отрицательных чисел)</span><span class="sxs-lookup"><span data-stu-id="b8305-169">Add a `+` character if the number is positive (to match a `-` sign for negatives)</span></span> |   |
| <span data-ttu-id="b8305-170">символ пробела</span><span class="sxs-lookup"><span data-stu-id="b8305-170">space character</span></span> | <span data-ttu-id="b8305-171">Добавить дополнительный пробел, если число является положительным (для сопоставления знака "-" для отрицательных чисел)</span><span class="sxs-lookup"><span data-stu-id="b8305-171">Add an extra space if the number is positive (to match a '-' sign for negatives)</span></span> |

<span data-ttu-id="b8305-172">Флаг printf `#` является недопустимым, и при его использовании будет выводиться сообщение об ошибке во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="b8305-172">The printf `#` flag is invalid and a compile-time error will be reported if it is used.</span></span>

<span data-ttu-id="b8305-173">Значения форматируются с использованием инвариантного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="b8305-173">Values are formatted using invariant culture.</span></span> <span data-ttu-id="b8305-174">Параметры языка и региональных параметров несущественны для `printf` форматирования, за исключением случаев, когда они влияют на результаты `%O` `%A` форматирования и.</span><span class="sxs-lookup"><span data-stu-id="b8305-174">Culture settings are irrelevant to `printf` formatting except when they affect the results of `%O` and `%A` formatting.</span></span> <span data-ttu-id="b8305-175">Дополнительные сведения см. в разделе [структурированное форматирование обычного текста](plaintext-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="b8305-175">For more information, see [structured plain text formatting](plaintext-formatting.md).</span></span>

## <a name="a-formatting"></a><span data-ttu-id="b8305-176">`%A`форматирован</span><span class="sxs-lookup"><span data-stu-id="b8305-176">`%A` formatting</span></span>

<span data-ttu-id="b8305-177">`%A`Описатель формата используется для форматирования значений в удобочитаемом виде и может быть полезен для создания отчетов о диагностических данных.</span><span class="sxs-lookup"><span data-stu-id="b8305-177">The `%A` format specifier is used to format values in a human-readable way, and can also be useful for reporting diagnostic information.</span></span>

### <a name="primitive-values"></a><span data-ttu-id="b8305-178">Примитивные значения</span><span class="sxs-lookup"><span data-stu-id="b8305-178">Primitive values</span></span>

<span data-ttu-id="b8305-179">При форматировании обычного текста с помощью `%A` спецификатора числовые значения F # форматируются с помощью суффикса и инвариантного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="b8305-179">When formatting plain text using the `%A` specifier, F# numeric values are formatted with their suffix and invariant culture.</span></span> <span data-ttu-id="b8305-180">Значения с плавающей запятой форматируются с использованием 10 точек точности с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="b8305-180">Floating point values are formatted using 10 places of floating point precision.</span></span> <span data-ttu-id="b8305-181">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-181">For example,</span></span>

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

<span data-ttu-id="b8305-182">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-182">produces</span></span>

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

<span data-ttu-id="b8305-183">При использовании `%A` спецификатора строки форматируются с помощью кавычек.</span><span class="sxs-lookup"><span data-stu-id="b8305-183">When using the `%A` specifier, strings are formatted using quotes.</span></span> <span data-ttu-id="b8305-184">Escape-коды не добавляются, а вместо них выводятся необработанные символы.</span><span class="sxs-lookup"><span data-stu-id="b8305-184">Escape codes are not added and instead the raw characters are printed.</span></span> <span data-ttu-id="b8305-185">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-185">For example,</span></span>

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

<span data-ttu-id="b8305-186">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-186">produces</span></span>

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a><span data-ttu-id="b8305-187">Значения .NET</span><span class="sxs-lookup"><span data-stu-id="b8305-187">.NET values</span></span>

<span data-ttu-id="b8305-188">При форматировании обычного текста с помощью `%A` спецификатора объекты .NET, отличные от F #, форматируются с помощью `x.ToString()` параметров по умолчанию .NET, заданных в `System.Globalization.CultureInfo.CurrentCulture` и `System.Globalization.CultureInfo.CurrentUICulture` .</span><span class="sxs-lookup"><span data-stu-id="b8305-188">When formatting plain text using the `%A` specifier, non-F# .NET objects are formatted by using `x.ToString()` using the default settings of .NET given by `System.Globalization.CultureInfo.CurrentCulture` and `System.Globalization.CultureInfo.CurrentUICulture`.</span></span>  <span data-ttu-id="b8305-189">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-189">For example,</span></span>

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

<span data-ttu-id="b8305-190">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-190">produces</span></span>

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a><span data-ttu-id="b8305-191">Структурированные значения</span><span class="sxs-lookup"><span data-stu-id="b8305-191">Structured values</span></span>

<span data-ttu-id="b8305-192">При форматировании обычного текста с помощью `%A` спецификатора для списков и кортежей F # используется отступ блока.</span><span class="sxs-lookup"><span data-stu-id="b8305-192">When formatting plain text using the `%A` specifier, block indentation is used for F# lists and tuples.</span></span> <span data-ttu-id="b8305-193">Это показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="b8305-193">This shown in the previous example.</span></span>
<span data-ttu-id="b8305-194">Также используется структура массивов, включая многомерные массивы.</span><span class="sxs-lookup"><span data-stu-id="b8305-194">The structure of arrays is also used, including multi-dimensional arrays.</span></span>  <span data-ttu-id="b8305-195">Одномерные массивы отображаются с `[| ... |]` синтаксисом.</span><span class="sxs-lookup"><span data-stu-id="b8305-195">Single-dimensional arrays are shown with `[| ... |]` syntax.</span></span> <span data-ttu-id="b8305-196">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-196">For example,</span></span>

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

<span data-ttu-id="b8305-197">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-197">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

<span data-ttu-id="b8305-198">Ширина печати по умолчанию — 80.</span><span class="sxs-lookup"><span data-stu-id="b8305-198">The default print width is 80.</span></span>  <span data-ttu-id="b8305-199">Эту ширину можно настроить с помощью ширины печати в описателе формата.</span><span class="sxs-lookup"><span data-stu-id="b8305-199">This width can be customized by using a print width in the format specifier.</span></span> <span data-ttu-id="b8305-200">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-200">For example,</span></span>

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

<span data-ttu-id="b8305-201">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-201">produces</span></span>

```console
[|(1, 1);
  (2, 4);
  (3, 9);
  (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4);
  (3, 9); (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
```

<span data-ttu-id="b8305-202">Если задать ширину печати, равную 0, то ширина печати не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="b8305-202">Specifying a print width of 0 results in no print width being used.</span></span> <span data-ttu-id="b8305-203">Будет выдаваться одна строка текста, за исключением тех случаев, когда в выходных данных содержатся разрывы строк.</span><span class="sxs-lookup"><span data-stu-id="b8305-203">A single line of text will result, except where embedded strings in the output contain line breaks.</span></span>  <span data-ttu-id="b8305-204">Пример</span><span class="sxs-lookup"><span data-stu-id="b8305-204">For example</span></span>

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

<span data-ttu-id="b8305-205">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-205">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

<span data-ttu-id="b8305-206">Ограничение глубины 4 используется для значений Sequence ( `IEnumerable` ), которые отображаются как `seq { ...}` .</span><span class="sxs-lookup"><span data-stu-id="b8305-206">A depth limit of 4 is used for sequence (`IEnumerable`) values, which are shown as `seq { ...}`.</span></span> <span data-ttu-id="b8305-207">Для списка и значений массива используется ограничение глубины 100.</span><span class="sxs-lookup"><span data-stu-id="b8305-207">A depth limit of 100 is used for list and array values.</span></span>
<span data-ttu-id="b8305-208">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-208">For example,</span></span>

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

<span data-ttu-id="b8305-209">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-209">produces</span></span>

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

<span data-ttu-id="b8305-210">Отступ блока также используется для структуры общих значений записей и объединений.</span><span class="sxs-lookup"><span data-stu-id="b8305-210">Block indentation is also used for the structure of public record and union values.</span></span> <span data-ttu-id="b8305-211">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-211">For example,</span></span>

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="b8305-212">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-212">produces</span></span>

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="b8305-213">Если `%+A` используется, то закрытая структура записей и объединений также раскрывается с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="b8305-213">If `%+A` is used, then the private structure of records and unions is also revealed by using reflection.</span></span> <span data-ttu-id="b8305-214">Пример</span><span class="sxs-lookup"><span data-stu-id="b8305-214">For example</span></span>

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

<span data-ttu-id="b8305-215">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-215">produces</span></span>

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a><span data-ttu-id="b8305-216">Большие, цикличные или глубоко вложенные значения</span><span class="sxs-lookup"><span data-stu-id="b8305-216">Large, cyclic, or deeply nested values</span></span>

<span data-ttu-id="b8305-217">Большие структурированные значения форматируются до максимального общего числа узлов объектов в 10000.</span><span class="sxs-lookup"><span data-stu-id="b8305-217">Large structured values are formatted to a maximum overall object node count of 10000.</span></span>
<span data-ttu-id="b8305-218">Глубоко вложенные значения форматируются в глубину 100.</span><span class="sxs-lookup"><span data-stu-id="b8305-218">Deeply nested values are formatted to a depth of 100.</span></span>  <span data-ttu-id="b8305-219">В обоих случаях `...` используется для елиде некоторых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b8305-219">In both cases `...` is used to elide some of the output.</span></span>  <span data-ttu-id="b8305-220">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-220">For example,</span></span>

```fsharp
type Tree =
    | Tip
    | Node of Tree * Tree

let rec make n =
    if n = 0 then
        Tip
    else
        Node(Tip, make (n-1))

printfn "%A" (make 1000)
```

<span data-ttu-id="b8305-221">создает большой выход с некоторыми частями неучтенный:</span><span class="sxs-lookup"><span data-stu-id="b8305-221">produces a large output with some parts elided:</span></span>

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

<span data-ttu-id="b8305-222">Циклы обнаруживаются на графах объектов и `...` используются в местах, где обнаруживаются циклы.</span><span class="sxs-lookup"><span data-stu-id="b8305-222">Cycles are detected in the object graphs and `...` is used at places where cycles are detected.</span></span> <span data-ttu-id="b8305-223">Пример</span><span class="sxs-lookup"><span data-stu-id="b8305-223">For example</span></span>

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

<span data-ttu-id="b8305-224">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-224">produces</span></span>

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a><span data-ttu-id="b8305-225">Значения "Lazy", "null" и "Function"</span><span class="sxs-lookup"><span data-stu-id="b8305-225">Lazy, null, and function values</span></span>

<span data-ttu-id="b8305-226">Отложенные значения выводятся в виде `Value is not created` или эквивалентного текста, если значение еще не было оценено.</span><span class="sxs-lookup"><span data-stu-id="b8305-226">Lazy values are printed as `Value is not created` or equivalent text when the value has not yet been evaluated.</span></span>

<span data-ttu-id="b8305-227">Значения NULL выводятся, как `null` если только статический тип значения не определен как тип объединения, где `null` является разрешенным представлением.</span><span class="sxs-lookup"><span data-stu-id="b8305-227">Null values are printed as `null` unless the static type of the value is determined to be a union type where `null` is a permitted representation.</span></span>

<span data-ttu-id="b8305-228">Значения функции F # выводятся в виде имени для внутреннего создания, например `<fun:it@43-7>` .</span><span class="sxs-lookup"><span data-stu-id="b8305-228">F# function values are printed as their internally generated closure name, for example, `<fun:it@43-7>`.</span></span>

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a><span data-ttu-id="b8305-229">Настроить форматирование обычного текста с помощью`StructuredFormatDisplay`</span><span class="sxs-lookup"><span data-stu-id="b8305-229">Customize plain text formatting with `StructuredFormatDisplay`</span></span>

<span data-ttu-id="b8305-230">При использовании `%A` спецификатора `StructuredFormatDisplay` учитывается присутствие атрибута в объявлениях типов.</span><span class="sxs-lookup"><span data-stu-id="b8305-230">When using the `%A` specifier, the presence of the `StructuredFormatDisplay` attribute on type declarations is respected.</span></span>  <span data-ttu-id="b8305-231">Это можно использовать для указания замещающего текста и свойства для вывода значения.</span><span class="sxs-lookup"><span data-stu-id="b8305-231">This can be used to specify surrogate text and property to display a value.</span></span> <span data-ttu-id="b8305-232">Пример:</span><span class="sxs-lookup"><span data-stu-id="b8305-232">For example:</span></span>

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

<span data-ttu-id="b8305-233">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-233">produces</span></span>

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a><span data-ttu-id="b8305-234">Настройка форматирования обычного текста путем переопределения`ToString`</span><span class="sxs-lookup"><span data-stu-id="b8305-234">Customize plain text formatting by overriding `ToString`</span></span>

<span data-ttu-id="b8305-235">Реализация по умолчанию `ToString` является наблюдаемой в программировании на F #.</span><span class="sxs-lookup"><span data-stu-id="b8305-235">The default implementation of `ToString` is observable in F# programming.</span></span> <span data-ttu-id="b8305-236">Часто результаты по умолчанию не подходят для использования в информации, отображаемой программистом, или в выходных данных пользователя, и поэтому обычно переопределяют реализацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b8305-236">Often, the default results aren't suitable for use in either programmer-facing information display or user output, and as a result it is common to override the default implementation.</span></span>  

<span data-ttu-id="b8305-237">По умолчанию записи и типы объединения F # переопределяют реализацию `ToString` с реализацией, которая использует `sprintf "%+A"` .</span><span class="sxs-lookup"><span data-stu-id="b8305-237">By default, F# record and union types override the implementation of `ToString` with an implementation that uses `sprintf "%+A"`.</span></span>  <span data-ttu-id="b8305-238">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-238">For example,</span></span>

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

<span data-ttu-id="b8305-239">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-239">produces</span></span>

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

<span data-ttu-id="b8305-240">Для типов классов реализация по умолчанию не `ToString` предоставляется, и используется значение по умолчанию .NET, которое сообщает имя типа.</span><span class="sxs-lookup"><span data-stu-id="b8305-240">For class types, no default implementation of `ToString` is provided and the .NET default is used, which reports the name of the type.</span></span> <span data-ttu-id="b8305-241">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b8305-241">For example,</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="b8305-242">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-242">produces</span></span>

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

<span data-ttu-id="b8305-243">Добавление переопределения для `ToString` может обеспечить лучшее форматирование.</span><span class="sxs-lookup"><span data-stu-id="b8305-243">Adding an override for `ToString` can give better formatting.</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="b8305-244">результатом</span><span class="sxs-lookup"><span data-stu-id="b8305-244">produces</span></span>

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="b8305-245">F# Interactive структурированной печати</span><span class="sxs-lookup"><span data-stu-id="b8305-245">F# Interactive structured printing</span></span>

<span data-ttu-id="b8305-246">F# Interactive ( `dotnet fsi` ) использует расширенную версию структурированного форматирования обычного текста для передачи значений и обеспечивает дополнительную настраиваемость.</span><span class="sxs-lookup"><span data-stu-id="b8305-246">F# Interactive (`dotnet fsi`) uses an extended version of structured plain text formatting to report values and allows additional customizability.</span></span> <span data-ttu-id="b8305-247">Дополнительные сведения см. в разделе [F# Interactive](fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="b8305-247">For more information, see [F# Interactive](fsharp-interactive-options.md).</span></span>

## <a name="customize-debug-displays"></a><span data-ttu-id="b8305-248">Настройка отображения отладки</span><span class="sxs-lookup"><span data-stu-id="b8305-248">Customize debug displays</span></span>

<span data-ttu-id="b8305-249">Отладчики для .NET используют атрибуты, такие как `DebuggerDisplay` и `DebuggerTypeProxy` , и они влияют на структурированное отображение объектов в окнах проверки отладчика.</span><span class="sxs-lookup"><span data-stu-id="b8305-249">Debuggers for .NET respect the use of attributes such as `DebuggerDisplay` and `DebuggerTypeProxy`, and these affect the structured display of objects in debugger inspection windows.</span></span>
<span data-ttu-id="b8305-250">Компилятор F # автоматически создал эти атрибуты для размеченных объединений и типов записей, но не для типов класса, интерфейса или структуры.</span><span class="sxs-lookup"><span data-stu-id="b8305-250">The F# compiler automatically generated these attributes for discriminated union and record types, but not class, interface, or struct types.</span></span>

<span data-ttu-id="b8305-251">Эти атрибуты не учитываются в форматировании обычного текста F #, но может быть полезно реализовать эти методы для улучшения отображения при отладке типов F #.</span><span class="sxs-lookup"><span data-stu-id="b8305-251">These attributes are ignored in F# plain text formatting, but it can be useful to implement these methods to improve displays when debugging F# types.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8305-252">См. также</span><span class="sxs-lookup"><span data-stu-id="b8305-252">See also</span></span>

- [<span data-ttu-id="b8305-253">Строки</span><span class="sxs-lookup"><span data-stu-id="b8305-253">Strings</span></span>](strings.md)
- [<span data-ttu-id="b8305-254">Записи</span><span class="sxs-lookup"><span data-stu-id="b8305-254">Records</span></span>](records.md)
- [<span data-ttu-id="b8305-255">Размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="b8305-255">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="b8305-256">F# Interactive</span><span class="sxs-lookup"><span data-stu-id="b8305-256">F# Interactive</span></span>](fsharp-interactive-options.md)
