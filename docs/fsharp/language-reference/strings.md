---
title: Строки
description: 'Узнайте, как тип "строка" F # представляет неизменяемый текст как последовательность символов Юникода.'
ms.date: 07/05/2019
ms.openlocfilehash: 67a6506b4b8c479da1022c069a7f53402f904b4d
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855417"
---
# <a name="strings"></a><span data-ttu-id="34f2e-103">Строки</span><span class="sxs-lookup"><span data-stu-id="34f2e-103">Strings</span></span>

<span data-ttu-id="34f2e-104">`string`Тип представляет неизменяемый текст как последовательность символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="34f2e-104">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="34f2e-105">`string` является псевдонимом для `System.String` в .NET.</span><span class="sxs-lookup"><span data-stu-id="34f2e-105">`string` is an alias for `System.String` in .NET.</span></span>

> [!NOTE]
> <span data-ttu-id="34f2e-106">Справочник по API docs.microsoft.com для F # не завершен.</span><span class="sxs-lookup"><span data-stu-id="34f2e-106">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="34f2e-107">Если вы столкнулись с неработающими ссылками, используйте [документацию по основной библиотеке F #](https://fsharp.github.io/fsharp-core-docs/) .</span><span class="sxs-lookup"><span data-stu-id="34f2e-107">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

## <a name="remarks"></a><span data-ttu-id="34f2e-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="34f2e-108">Remarks</span></span>

<span data-ttu-id="34f2e-109">Строковые литералы разделяются символом кавычки (").</span><span class="sxs-lookup"><span data-stu-id="34f2e-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="34f2e-110">Символ обратной косой черты ( \\ ) используется для кодирования определенных специальных символов.</span><span class="sxs-lookup"><span data-stu-id="34f2e-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="34f2e-111">Обратная косая черта и следующий символ вместе называются *escape-последовательностью*.</span><span class="sxs-lookup"><span data-stu-id="34f2e-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="34f2e-112">В следующей таблице показаны escape-последовательности, поддерживаемые в строковых литералах F #.</span><span class="sxs-lookup"><span data-stu-id="34f2e-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="34f2e-113">Знак</span><span class="sxs-lookup"><span data-stu-id="34f2e-113">Character</span></span>|<span data-ttu-id="34f2e-114">Escape-последовательность</span><span class="sxs-lookup"><span data-stu-id="34f2e-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="34f2e-115">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="34f2e-115">Alert</span></span>|`\a`|
|<span data-ttu-id="34f2e-116">Backspace</span><span class="sxs-lookup"><span data-stu-id="34f2e-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="34f2e-117">Перевод страницы</span><span class="sxs-lookup"><span data-stu-id="34f2e-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="34f2e-118">Новая строка</span><span class="sxs-lookup"><span data-stu-id="34f2e-118">Newline</span></span>|`\n`|
|<span data-ttu-id="34f2e-119">Возврат каретки</span><span class="sxs-lookup"><span data-stu-id="34f2e-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="34f2e-120">Вкладка</span><span class="sxs-lookup"><span data-stu-id="34f2e-120">Tab</span></span>|`\t`|
|<span data-ttu-id="34f2e-121">Вертикальная табуляция</span><span class="sxs-lookup"><span data-stu-id="34f2e-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="34f2e-122">Обратная косая черта</span><span class="sxs-lookup"><span data-stu-id="34f2e-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="34f2e-123">Знак кавычек</span><span class="sxs-lookup"><span data-stu-id="34f2e-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="34f2e-124">Апостроф</span><span class="sxs-lookup"><span data-stu-id="34f2e-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="34f2e-125">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="34f2e-125">Unicode character</span></span>|<span data-ttu-id="34f2e-126">`\DDD`(где `D` обозначает десятичную цифру, диапазон 000-255, например `\231` = "c")</span><span class="sxs-lookup"><span data-stu-id="34f2e-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="34f2e-127">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="34f2e-127">Unicode character</span></span>|<span data-ttu-id="34f2e-128">`\xHH`(где `H` обозначает шестнадцатеричную цифру; диапазон от 00 до FF; например, `\xE7` = "c")</span><span class="sxs-lookup"><span data-stu-id="34f2e-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="34f2e-129">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="34f2e-129">Unicode character</span></span>|<span data-ttu-id="34f2e-130">`\uHHHH`(UTF-16) (где `H` обозначает шестнадцатеричную цифру, диапазон — 0000-FFFF;  Например, `\u00E7` = "c")</span><span class="sxs-lookup"><span data-stu-id="34f2e-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="34f2e-131">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="34f2e-131">Unicode character</span></span>|<span data-ttu-id="34f2e-132">`\U00HHHHHH`(UTF-32) (где `H` обозначает шестнадцатеричную цифру, диапазон 000000-10FFFF;  Например, `\U0001F47D` = " 👽 ")</span><span class="sxs-lookup"><span data-stu-id="34f2e-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="34f2e-133">`\DDD`Escape-последовательность — десятичная нотация, а не восьмеричная нотация, как в большинстве других языков.</span><span class="sxs-lookup"><span data-stu-id="34f2e-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="34f2e-134">Таким образом, цифры `8` и `9` являются допустимыми, а последовательность `\032` представляет пробел (U + 0020), тогда как в восьмеричной нотации будет использоваться та же кодовая точка `\040` .</span><span class="sxs-lookup"><span data-stu-id="34f2e-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="34f2e-135">Если ограничиться диапазоном 0-255 (0xFF), то `\DDD` `\x` escape-последовательности по сути являются набором символов [ISO – 8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) , так как они соответствуют первым 256 кодовых позиций Юникода.</span><span class="sxs-lookup"><span data-stu-id="34f2e-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="34f2e-136">Буквальные строки</span><span class="sxs-lookup"><span data-stu-id="34f2e-136">Verbatim Strings</span></span>

<span data-ttu-id="34f2e-137">Если предшествует символ @, литерал является буквальной строкой.</span><span class="sxs-lookup"><span data-stu-id="34f2e-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="34f2e-138">Это означает, что все escape-последовательности игнорируются, за исключением того, что две кавычки считаются символом одной кавычки.</span><span class="sxs-lookup"><span data-stu-id="34f2e-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="34f2e-139">Строки с тройным заключенным в кавычки</span><span class="sxs-lookup"><span data-stu-id="34f2e-139">Triple Quoted Strings</span></span>

<span data-ttu-id="34f2e-140">Кроме того, строка может быть заключена в тройные кавычки.</span><span class="sxs-lookup"><span data-stu-id="34f2e-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="34f2e-141">В этом случае все escape-последовательности игнорируются, включая двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="34f2e-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="34f2e-142">Чтобы указать строку, содержащую внедренную строку в кавычках, можно использовать буквальную строку или строку с тройными кавычками.</span><span class="sxs-lookup"><span data-stu-id="34f2e-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="34f2e-143">При использовании буквальной строки необходимо указать две кавычки, чтобы указать символ одинарной кавычки.</span><span class="sxs-lookup"><span data-stu-id="34f2e-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="34f2e-144">При использовании строки, заключенной в тройные кавычки, можно использовать символы одинарной кавычки без синтаксического анализа в качестве конца строки.</span><span class="sxs-lookup"><span data-stu-id="34f2e-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="34f2e-145">Этот метод может быть полезен при работе с XML или с другими структурами, включающими в себя внедренные кавычки.</span><span class="sxs-lookup"><span data-stu-id="34f2e-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="34f2e-146">В коде строки, имеющие разрывы строк, принимаются, а разрывы строк интерпретируется как символы новой строки, если только символ обратной косой черты не является последним символом перед разрывом строки.</span><span class="sxs-lookup"><span data-stu-id="34f2e-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="34f2e-147">Начальные пробелы в следующей строке игнорируются при использовании символа обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="34f2e-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="34f2e-148">Следующий код создает строку со `str1` значением `"abc\ndef"` и строкой `str2` , имеющей значение `"abcdef"` .</span><span class="sxs-lookup"><span data-stu-id="34f2e-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="34f2e-149">Индексирование строк и создание срезов</span><span class="sxs-lookup"><span data-stu-id="34f2e-149">String Indexing and Slicing</span></span>

<span data-ttu-id="34f2e-150">Получить доступ к отдельным символам в строке можно с помощью синтаксиса, подобного массиву, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="34f2e-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="34f2e-151">В результате получается `b`.</span><span class="sxs-lookup"><span data-stu-id="34f2e-151">The output is `b`.</span></span>

<span data-ttu-id="34f2e-152">Кроме того, можно извлечь подстроки с помощью синтаксиса среза массива, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="34f2e-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="34f2e-153">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="34f2e-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="34f2e-154">Строки ASCII можно представлять массивами беззнаковых байтов типа `byte[]` .</span><span class="sxs-lookup"><span data-stu-id="34f2e-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="34f2e-155">Добавьте суффикс `B` к строковому литералу, чтобы указать, что это строка ASCII.</span><span class="sxs-lookup"><span data-stu-id="34f2e-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="34f2e-156">Строковые литералы ASCII, используемые с массивами байтов, поддерживают те же escape-последовательности, что и строки в Юникоде, за исключением escape-последовательностей Юникода.</span><span class="sxs-lookup"><span data-stu-id="34f2e-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="34f2e-157">Строковые операторы</span><span class="sxs-lookup"><span data-stu-id="34f2e-157">String Operators</span></span>

<span data-ttu-id="34f2e-158">`+`Оператор можно использовать для сцепления строк, сохраняя совместимость с функциями обработки строк .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="34f2e-158">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="34f2e-159">В следующем примере показано объединение строк.</span><span class="sxs-lookup"><span data-stu-id="34f2e-159">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="34f2e-160">Класс String</span><span class="sxs-lookup"><span data-stu-id="34f2e-160">String Class</span></span>

<span data-ttu-id="34f2e-161">Так как тип строки в F # фактически является типом .NET Framework `System.String` , `System.String` доступны все элементы.</span><span class="sxs-lookup"><span data-stu-id="34f2e-161">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="34f2e-162">Сюда входит `+` оператор, который используется для сцепления строк, `Length` Свойства и `Chars` свойства, которые возвращают строку в виде массива символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="34f2e-162">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="34f2e-163">Дополнительные сведения о строках см. в разделе `System.String` .</span><span class="sxs-lookup"><span data-stu-id="34f2e-163">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="34f2e-164">С помощью `Chars` свойства объекта `System.String` можно получить доступ к отдельным символам в строке, указав индекс, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="34f2e-164">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="34f2e-165">Строковый модуль</span><span class="sxs-lookup"><span data-stu-id="34f2e-165">String Module</span></span>

<span data-ttu-id="34f2e-166">Дополнительные функции обработки строк включаются в `String` модуль в `FSharp.Core` пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="34f2e-166">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="34f2e-167">Дополнительные сведения см. в разделе [Модуль Core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="34f2e-167">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="34f2e-168">См. также</span><span class="sxs-lookup"><span data-stu-id="34f2e-168">See also</span></span>

- [<span data-ttu-id="34f2e-169">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="34f2e-169">F# Language Reference</span></span>](index.md)
