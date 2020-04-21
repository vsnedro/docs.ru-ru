---
title: Строки
description: Узнайте, как тип «строки» F's представляет собой неизменяемый текст в виде последовательности символов Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: 242a2cefa1cce8995090dddd1d1fd7181e0f5e0c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739568"
---
# <a name="strings"></a><span data-ttu-id="0415d-103">Строки</span><span class="sxs-lookup"><span data-stu-id="0415d-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="0415d-104">Ссылки на справочник по API в этой статье ведут на сайт MSDN.</span><span class="sxs-lookup"><span data-stu-id="0415d-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="0415d-105">Работа над справочником по API docs.microsoft.com не завершена.</span><span class="sxs-lookup"><span data-stu-id="0415d-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="0415d-106">Тип `string` представляет собой неизменяемый текст как последовательность символов Unicode.</span><span class="sxs-lookup"><span data-stu-id="0415d-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="0415d-107">`string` — это псевдоним для `System.String` в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0415d-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="0415d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0415d-108">Remarks</span></span>

<span data-ttu-id="0415d-109">Строки буквальные знаки разграничены характером кавычки () .</span><span class="sxs-lookup"><span data-stu-id="0415d-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="0415d-110">Символ backslash \\ () используется для кодирования определенных специальных символов.</span><span class="sxs-lookup"><span data-stu-id="0415d-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="0415d-111">Backslash и следующий символ вместе известны как *побег последовательности*.</span><span class="sxs-lookup"><span data-stu-id="0415d-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="0415d-112">Последовательности побега, поддерживаемые в буквах строки F', отображаются в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="0415d-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="0415d-113">Символ</span><span class="sxs-lookup"><span data-stu-id="0415d-113">Character</span></span>|<span data-ttu-id="0415d-114">Escape-последовательность</span><span class="sxs-lookup"><span data-stu-id="0415d-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="0415d-115">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="0415d-115">Alert</span></span>|`\a`|
|<span data-ttu-id="0415d-116">Отмена</span><span class="sxs-lookup"><span data-stu-id="0415d-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="0415d-117">Подача страницы</span><span class="sxs-lookup"><span data-stu-id="0415d-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="0415d-118">Новая строка</span><span class="sxs-lookup"><span data-stu-id="0415d-118">Newline</span></span>|`\n`|
|<span data-ttu-id="0415d-119">Возврат каретки</span><span class="sxs-lookup"><span data-stu-id="0415d-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="0415d-120">Вкладка</span><span class="sxs-lookup"><span data-stu-id="0415d-120">Tab</span></span>|`\t`|
|<span data-ttu-id="0415d-121">Вертикальная табуляция</span><span class="sxs-lookup"><span data-stu-id="0415d-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="0415d-122">Обратная косая черта</span><span class="sxs-lookup"><span data-stu-id="0415d-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="0415d-123">Знак кавычек</span><span class="sxs-lookup"><span data-stu-id="0415d-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="0415d-124">Апостроф</span><span class="sxs-lookup"><span data-stu-id="0415d-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="0415d-125">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="0415d-125">Unicode character</span></span>|<span data-ttu-id="0415d-126">`\DDD`(где `D` указывается десятичная цифра; диапазон 000 - 255; например, `\231` q "q")</span><span class="sxs-lookup"><span data-stu-id="0415d-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="0415d-127">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="0415d-127">Unicode character</span></span>|<span data-ttu-id="0415d-128">`\xHH`(где `H` указывается гексадецимальная цифра; диапазон 00 `\xE7` - FF; например, q "q")</span><span class="sxs-lookup"><span data-stu-id="0415d-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="0415d-129">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="0415d-129">Unicode character</span></span>|<span data-ttu-id="0415d-130">`\uHHHH`(UTF-16) (где `H` указываетг гексадецимальная цифра; диапазон 0000 - FFFF;  например, `\u00E7` "кв")</span><span class="sxs-lookup"><span data-stu-id="0415d-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="0415d-131">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="0415d-131">Unicode character</span></span>|<span data-ttu-id="0415d-132">`\U00HHHHHH`(UTF-32) (где `H` указываетг гексадецимальная цифра; диапазон 000000 - 10FFFF;  например, `\U0001F47D` «»👽« »)</span><span class="sxs-lookup"><span data-stu-id="0415d-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="0415d-133">Последовательность `\DDD` побега является десятичной нотации, а не октальной нотации, как в большинстве других языков.</span><span class="sxs-lookup"><span data-stu-id="0415d-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="0415d-134">Таким образом, `8` `9` цифры и являются `\032` действительными, и последовательность представляет пространство (U'0020), в `\040`то время как тот же кодовый пункт в октальной нотации будет .</span><span class="sxs-lookup"><span data-stu-id="0415d-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="0415d-135">Будучи ограниченным к диапазону 0 - 255 `\DDD` (0xFF), и `\x` последовательности побега фактически [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) набор символов, так как что соответствует первым 256 Unicode кодовых точек.</span><span class="sxs-lookup"><span data-stu-id="0415d-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="0415d-136">Дословные струны</span><span class="sxs-lookup"><span data-stu-id="0415d-136">Verbatim Strings</span></span>

<span data-ttu-id="0415d-137">Если предшествует символ а, буквальный является дословной строки.</span><span class="sxs-lookup"><span data-stu-id="0415d-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="0415d-138">Это означает, что любые последовательности побега игнорируются, за исключением того, что два символа метки цитатинтерно интерпретируются как один символ метки цитаты.</span><span class="sxs-lookup"><span data-stu-id="0415d-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="0415d-139">Тройные цитируемые струны</span><span class="sxs-lookup"><span data-stu-id="0415d-139">Triple Quoted Strings</span></span>

<span data-ttu-id="0415d-140">Кроме того, строка может быть заключена тройными котировками.</span><span class="sxs-lookup"><span data-stu-id="0415d-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="0415d-141">В этом случае все последовательности побега игнорируются, включая символы двойной отметки цитаты.</span><span class="sxs-lookup"><span data-stu-id="0415d-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="0415d-142">Чтобы указать строку, содержащую встроенную строку, можно использовать дословную строку или тройную строку.</span><span class="sxs-lookup"><span data-stu-id="0415d-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="0415d-143">Если вы используете строку стенографии, необходимо указать два символа метки цитаты, чтобы указать один символ метки цитаты.</span><span class="sxs-lookup"><span data-stu-id="0415d-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="0415d-144">Если вы используете строку с тройным капотом, вы можете использовать символы одной метки цитаты без их разогнания в конце строки.</span><span class="sxs-lookup"><span data-stu-id="0415d-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="0415d-145">Этот метод может быть полезен при работе с XML или другими структурами, которые включают встроенные кавычки.</span><span class="sxs-lookup"><span data-stu-id="0415d-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="0415d-146">В коде принимаются строки с разрывами строк, а разрывы строк интерпретируются буквально как новые линии, если только символ backslash не является последним символом перед разрывом строки.</span><span class="sxs-lookup"><span data-stu-id="0415d-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="0415d-147">Ведущее белое пространство на следующей строке игнорируется при использовании символа backslash.</span><span class="sxs-lookup"><span data-stu-id="0415d-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="0415d-148">Следующий код создает `str1` строку, которая `str2` имеет `"abcdef"`значение `"abc\ndef"` и строку, которая имеет значение.</span><span class="sxs-lookup"><span data-stu-id="0415d-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="0415d-149">Индексирование строк и нарезка</span><span class="sxs-lookup"><span data-stu-id="0415d-149">String Indexing and Slicing</span></span>

<span data-ttu-id="0415d-150">Вы можете получить доступ к отдельным символам в строке, используя массив, как синтаксис, следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0415d-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="0415d-151">В результате получается `b`.</span><span class="sxs-lookup"><span data-stu-id="0415d-151">The output is `b`.</span></span>

<span data-ttu-id="0415d-152">Или вы можете извлечь подстроки с помощью синтаксиса срезов массива, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0415d-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="0415d-153">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0415d-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="0415d-154">Вы можете представлять строки ASCII по массивам `byte[]`неподписанных байтов, введите тип.</span><span class="sxs-lookup"><span data-stu-id="0415d-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="0415d-155">Вы добавляете суффикс `B` в строку буквально, чтобы указать, что это строка ASCII.</span><span class="sxs-lookup"><span data-stu-id="0415d-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="0415d-156">Буквальные буквы ASCII, используемые с байт-массивами, поддерживают те же последовательности побега, что и строки Unicode, за исключением последовательностей выхода Unicode.</span><span class="sxs-lookup"><span data-stu-id="0415d-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="0415d-157">Операторы струнных</span><span class="sxs-lookup"><span data-stu-id="0415d-157">String Operators</span></span>

<span data-ttu-id="0415d-158">Оператор `+` может использоваться для совмещения строк, сохраняя совместимость с функциями обработки строк .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0415d-158">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="0415d-159">Следующий пример иллюстрирует конкатацию строки.</span><span class="sxs-lookup"><span data-stu-id="0415d-159">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="0415d-160">Струнный класс</span><span class="sxs-lookup"><span data-stu-id="0415d-160">String Class</span></span>

<span data-ttu-id="0415d-161">Поскольку тип строки в F-на `System.String` самом деле `System.String` является типом рамочного соглашения .NET, все участники доступны.</span><span class="sxs-lookup"><span data-stu-id="0415d-161">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="0415d-162">Это включает `+` в себя оператора, который используется для `Length` совмещения строк, свойство и `Chars` свойство, которое возвращает строку в виде массива символов Unicode.</span><span class="sxs-lookup"><span data-stu-id="0415d-162">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="0415d-163">Для получения дополнительной информации `System.String`о строках см.</span><span class="sxs-lookup"><span data-stu-id="0415d-163">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="0415d-164">Используя `Chars` `System.String`свойство, вы можете получить доступ к отдельным символам в строке, указав индекс, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0415d-164">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="0415d-165">Струнный модуль</span><span class="sxs-lookup"><span data-stu-id="0415d-165">String Module</span></span>

<span data-ttu-id="0415d-166">Дополнительная функциональность для обработки `String` строк `FSharp.Core` включена в модуль в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="0415d-166">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="0415d-167">Для получения дополнительной информации [см.](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)</span><span class="sxs-lookup"><span data-stu-id="0415d-167">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="0415d-168">См. также</span><span class="sxs-lookup"><span data-stu-id="0415d-168">See also</span></span>

- [<span data-ttu-id="0415d-169">Ссылка на язык F</span><span class="sxs-lookup"><span data-stu-id="0415d-169">F# Language Reference</span></span>](index.md)
