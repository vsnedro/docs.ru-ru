---
title: Разделение строк на подстроки
description: Узнайте о различных методах для извлечения частей строки, в том числе о String.Split, регулярных выражениях и String.Substring.
ms.date: 10/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], breaking up
ms.openlocfilehash: 88947c4576b0496e4b4e45042d665e3ca5857c53
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93403485"
---
# <a name="extract-substrings-from-a-string"></a><span data-ttu-id="88fc8-103">Извлечение подстрок из строки</span><span class="sxs-lookup"><span data-stu-id="88fc8-103">Extract substrings from a string</span></span>

<span data-ttu-id="88fc8-104">В этой статье рассматриваются различные методы извлечения частей строки.</span><span class="sxs-lookup"><span data-stu-id="88fc8-104">This article covers some different techniques for extracting parts of a string.</span></span>

- <span data-ttu-id="88fc8-105">Используйте [метод Split](#stringsplit-method), если нужные подстроки разделены символом-разделителем (или символами).</span><span class="sxs-lookup"><span data-stu-id="88fc8-105">Use the [Split method](#stringsplit-method) when the substrings you want are separated by a known delimiting character (or characters).</span></span>
- <span data-ttu-id="88fc8-106">[Регулярные выражения](#regular-expressions) удобно использовать, когда строка соответствует фиксированному шаблону.</span><span class="sxs-lookup"><span data-stu-id="88fc8-106">[Regular expressions](#regular-expressions) are useful when the string conforms to a fixed pattern.</span></span>
- <span data-ttu-id="88fc8-107">Используйте сочетание [методов IndexOf и Substring](#stringindexof-and-stringsubstring-methods), если не хотите извлекать *все* подстроки из строки.</span><span class="sxs-lookup"><span data-stu-id="88fc8-107">Use the [IndexOf and Substring methods](#stringindexof-and-stringsubstring-methods) in conjunction when you don't want to extract *all* of the substrings in a string.</span></span>

## <a name="stringsplit-method"></a><span data-ttu-id="88fc8-108">Метод String.Split</span><span class="sxs-lookup"><span data-stu-id="88fc8-108">String.Split method</span></span>

<span data-ttu-id="88fc8-109"><xref:System.String.Split%2A?displayProperty=nameWithType> предоставляет несколько перегрузок, которые позволяют разбить строку на группу подстрок, основанных на одном или нескольких указанных символах-разделителях.</span><span class="sxs-lookup"><span data-stu-id="88fc8-109"><xref:System.String.Split%2A?displayProperty=nameWithType> provides a handful of overloads to help you break up a string into a group of substrings based on one or more delimiting characters that you specify.</span></span> <span data-ttu-id="88fc8-110">Вы можете ограничить общее число подстрок в окончательном результате, обрезав пробелы в подстроках или исключив пустые подстроки.</span><span class="sxs-lookup"><span data-stu-id="88fc8-110">You can choose to limit the total number of substrings in the final result, trim white-space characters from substrings, or exclude empty substrings.</span></span>

<span data-ttu-id="88fc8-111">Ниже показаны три различные перегрузки `String.Split()`.</span><span class="sxs-lookup"><span data-stu-id="88fc8-111">The following examples show three different overloads of `String.Split()`.</span></span> <span data-ttu-id="88fc8-112">Первый пример вызывает перегрузку <xref:System.String.Split(System.Char[])> без передачи знаков разделения.</span><span class="sxs-lookup"><span data-stu-id="88fc8-112">The first example calls the <xref:System.String.Split(System.Char[])> overload without passing any separator characters.</span></span> <span data-ttu-id="88fc8-113">Если не указать символы-разделители, `String.Split()` будет использовать для разделения строки разделители по умолчанию, которые являются пробелами.</span><span class="sxs-lookup"><span data-stu-id="88fc8-113">When you don't specify any delimiting characters, `String.Split()` uses default delimiters, which are white-space characters, to split up the string.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#1)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="1":::

<span data-ttu-id="88fc8-114">Как видите, символы-точки (`.`) содержатся в двух подстроках.</span><span class="sxs-lookup"><span data-stu-id="88fc8-114">As you can see, the period characters (`.`) are included in two of the substrings.</span></span> <span data-ttu-id="88fc8-115">Если вы хотите исключить символы-точки, добавьте символ-точку как дополнительный символ разделителя.</span><span class="sxs-lookup"><span data-stu-id="88fc8-115">If you want to exclude the period characters, you can add the period character as an additional delimiting character.</span></span> <span data-ttu-id="88fc8-116">В следующем примере показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="88fc8-116">The next example shows how to do this.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#2)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="2":::

<span data-ttu-id="88fc8-117">Точки исчезли из подстрок, однако теперь появились две дополнительные пустые подстроки.</span><span class="sxs-lookup"><span data-stu-id="88fc8-117">The periods are gone from the substrings, but now two extra empty substrings have been included.</span></span> <span data-ttu-id="88fc8-118">Пустые подстроки представляют подстроку между словом и точкой после него.</span><span class="sxs-lookup"><span data-stu-id="88fc8-118">These empty substring represent the substring between the word and the period that follows it.</span></span> <span data-ttu-id="88fc8-119">Чтобы исключить из результирующего массива пустые подстроки, вызовите перегрузку <xref:System.String.Split(System.Char[],System.StringSplitOptions)> и укажите <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> для параметра `options`.</span><span class="sxs-lookup"><span data-stu-id="88fc8-119">To omit empty substrings from the resulting array, you can call the <xref:System.String.Split(System.Char[],System.StringSplitOptions)> overload and specify <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> for the `options` parameter.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#3)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="3":::

## <a name="regular-expressions"></a><span data-ttu-id="88fc8-120">Регулярные выражения</span><span class="sxs-lookup"><span data-stu-id="88fc8-120">Regular expressions</span></span>

<span data-ttu-id="88fc8-121">Если строка соответствует фиксированному шаблону, используйте регулярное выражение для извлечения и обработки ее элементов.</span><span class="sxs-lookup"><span data-stu-id="88fc8-121">If your string conforms to a fixed pattern, you can use a regular expression to extract and handle its elements.</span></span> <span data-ttu-id="88fc8-122">Например, если строки имеют форму " *номер* *операнд* *номер* ", тогда для извлечения и обработки элементов строки можно использовать [регулярное выражение](regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="88fc8-122">For example, if strings take the form " *number* *operand* *number* ", you can use a [regular expression](regular-expressions.md) to extract and handle the string's elements.</span></span> <span data-ttu-id="88fc8-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="88fc8-123">Here's an example:</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="1":::

<span data-ttu-id="88fc8-124">Шаблон регулярного выражения `(\d+)\s+([-+*/])\s+(\d+)` определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="88fc8-124">The regular expression pattern `(\d+)\s+([-+*/])\s+(\d+)` is defined like this:</span></span>

|<span data-ttu-id="88fc8-125">Шаблон</span><span class="sxs-lookup"><span data-stu-id="88fc8-125">Pattern</span></span>|<span data-ttu-id="88fc8-126">Описание</span><span class="sxs-lookup"><span data-stu-id="88fc8-126">Description</span></span>|
|-------------|-----------------|
|`(\d+)`|<span data-ttu-id="88fc8-127">Совпадение с одной или несколькими десятичными цифрами.</span><span class="sxs-lookup"><span data-stu-id="88fc8-127">Match one or more decimal digits.</span></span> <span data-ttu-id="88fc8-128">Это первая группа записи.</span><span class="sxs-lookup"><span data-stu-id="88fc8-128">This is the first capturing group.</span></span>|
|`\s+`|<span data-ttu-id="88fc8-129">Совпадение с одним или несколькими пробелами.</span><span class="sxs-lookup"><span data-stu-id="88fc8-129">Match one or more white-space characters.</span></span>|
|`([-+*/])`|<span data-ttu-id="88fc8-130">Совпадение со знаком арифметического оператора (+, -, \*, или /).</span><span class="sxs-lookup"><span data-stu-id="88fc8-130">Match an arithmetic operator sign (+, -, \*, or /).</span></span> <span data-ttu-id="88fc8-131">Это вторая группа записи.</span><span class="sxs-lookup"><span data-stu-id="88fc8-131">This is the second capturing group.</span></span>|
|`\s+`|<span data-ttu-id="88fc8-132">Совпадение с одним или несколькими пробелами.</span><span class="sxs-lookup"><span data-stu-id="88fc8-132">Match one or more white-space characters.</span></span>|
|`(\d+)`|<span data-ttu-id="88fc8-133">Совпадение с одной или несколькими десятичными цифрами.</span><span class="sxs-lookup"><span data-stu-id="88fc8-133">Match one or more decimal digits.</span></span> <span data-ttu-id="88fc8-134">Это третья группа записи.</span><span class="sxs-lookup"><span data-stu-id="88fc8-134">This is the third capturing group.</span></span>|

<span data-ttu-id="88fc8-135">Вы также можете использовать регулярное выражение для извлечения подстрок из строки на основе шаблона, а не фиксированного набора символов.</span><span class="sxs-lookup"><span data-stu-id="88fc8-135">You can also use a regular expression to extract substrings from a string based on a pattern rather than a fixed set of characters.</span></span> <span data-ttu-id="88fc8-136">Это распространенный сценарий, если происходит одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="88fc8-136">This is a common scenario when either of these conditions occurs:</span></span>

- <span data-ttu-id="88fc8-137">Один или несколько символов-разделителей не *всегда* служат разделителями в экземпляре <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="88fc8-137">One or more of the delimiter characters does not *always* serve as a delimiter in the <xref:System.String> instance.</span></span>

- <span data-ttu-id="88fc8-138">Последовательность и количество символов-разделителей являются изменяемыми или неизвестными.</span><span class="sxs-lookup"><span data-stu-id="88fc8-138">The sequence and number of delimiter characters is variable or unknown.</span></span>

<span data-ttu-id="88fc8-139">Например, метод <xref:System.String.Split%2A> нельзя использовать для разделения следующей строки, поскольку число символов `\n` (новая строка) является изменяемым и они не всегда являются разделителями.</span><span class="sxs-lookup"><span data-stu-id="88fc8-139">For example, the <xref:System.String.Split%2A> method cannot be used to split the following string, because the number of `\n` (newline) characters is variable, and they don't always serve as delimiters.</span></span>

```text
[This is captured\ntext.]\n\n[\n[This is more captured text.]\n]
\n[Some more captured text:\n   Option1\n   Option2][Terse text.]
```

<span data-ttu-id="88fc8-140">Регулярное выражение может легко разделить эту строку, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="88fc8-140">A regular expression can split this string easily, as the following example shows.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="2" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="2":::

<span data-ttu-id="88fc8-141">Шаблон регулярного выражения `\[([^\[\]]+)\]` определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="88fc8-141">The regular expression pattern `\[([^\[\]]+)\]` is defined like this:</span></span>

|<span data-ttu-id="88fc8-142">Шаблон</span><span class="sxs-lookup"><span data-stu-id="88fc8-142">Pattern</span></span>|<span data-ttu-id="88fc8-143">Описание</span><span class="sxs-lookup"><span data-stu-id="88fc8-143">Description</span></span>|
|-------------|-----------------|
|`\[`|<span data-ttu-id="88fc8-144">Совпадение с открывающей скобой.</span><span class="sxs-lookup"><span data-stu-id="88fc8-144">Match an opening bracket.</span></span>|
|`([^\[\]]+)`|<span data-ttu-id="88fc8-145">Совпадение с любым символом, который не является открывающей или закрывающей скобкой, один или несколько раз.</span><span class="sxs-lookup"><span data-stu-id="88fc8-145">Match any character that is not an opening or a closing bracket one or more times.</span></span> <span data-ttu-id="88fc8-146">Это первая группа записи.</span><span class="sxs-lookup"><span data-stu-id="88fc8-146">This is the first capturing group.</span></span>|
|`\]`|<span data-ttu-id="88fc8-147">Совпадение с закрывающей скобкой.</span><span class="sxs-lookup"><span data-stu-id="88fc8-147">Match a closing bracket.</span></span>|

<span data-ttu-id="88fc8-148">Метод <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> практически идентичен методу <xref:System.String.Split%2A?displayProperty=nameWithType>, за исключением того, что он разделяет строку на основе шаблона регулярного выражения, а не фиксированной кодировки.</span><span class="sxs-lookup"><span data-stu-id="88fc8-148">The <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method is almost identical to <xref:System.String.Split%2A?displayProperty=nameWithType>, except that it splits a string based on a regular expression pattern instead of a fixed character set.</span></span> <span data-ttu-id="88fc8-149">Например, в следующем примере метод <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> используется для разделения строки, которая содержит подстроки, разделенные с помощью различных сочетаний дефисов и других символов.</span><span class="sxs-lookup"><span data-stu-id="88fc8-149">For example, the following example uses the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to split a string that contains substrings delimited by various combinations of hyphens and other characters.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="3" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="3":::

<span data-ttu-id="88fc8-150">Шаблон регулярного выражения `\s-\s?[+*]?\s?-\s` определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="88fc8-150">The regular expression pattern `\s-\s?[+*]?\s?-\s` is defined like this:</span></span>

|<span data-ttu-id="88fc8-151">Шаблон</span><span class="sxs-lookup"><span data-stu-id="88fc8-151">Pattern</span></span>|<span data-ttu-id="88fc8-152">Описание</span><span class="sxs-lookup"><span data-stu-id="88fc8-152">Description</span></span>|
|-------------|-----------------|
|`\s-`|<span data-ttu-id="88fc8-153">Совпадение с пробелом, за которым следует дефис.</span><span class="sxs-lookup"><span data-stu-id="88fc8-153">Match a white-space character followed by a hyphen.</span></span>|
|`\s?`|<span data-ttu-id="88fc8-154">Совпадение с нулем или одним символом пробела.</span><span class="sxs-lookup"><span data-stu-id="88fc8-154">Match zero or one white-space character.</span></span>|
|`[+*]?`|<span data-ttu-id="88fc8-155">Совпадение с нулем или единичное появление символа + или \*.</span><span class="sxs-lookup"><span data-stu-id="88fc8-155">Match zero or one occurrence of either the + or \* character.</span></span>|
|`\s?`|<span data-ttu-id="88fc8-156">Совпадение с нулем или одним символом пробела.</span><span class="sxs-lookup"><span data-stu-id="88fc8-156">Match zero or one white-space character.</span></span>|
|`-\s`|<span data-ttu-id="88fc8-157">Совпадение с дефисом, за которым следует пробел.</span><span class="sxs-lookup"><span data-stu-id="88fc8-157">Match a hyphen followed by a white-space character.</span></span>|

## <a name="stringindexof-and-stringsubstring-methods"></a><span data-ttu-id="88fc8-158">Методы String.IndexOf и String.Substring</span><span class="sxs-lookup"><span data-stu-id="88fc8-158">String.IndexOf and String.Substring methods</span></span>

<span data-ttu-id="88fc8-159">Если вам нужны все подстроки в строке, можете использовать один из методов сравнения строк, которые возвращают индекс начала сопоставления.</span><span class="sxs-lookup"><span data-stu-id="88fc8-159">If you aren't interested in all of the substrings in a string, you might prefer to work with one of the string comparison methods that returns the index at which the match begins.</span></span> <span data-ttu-id="88fc8-160">Затем для извлечения нужных подстрок можно будет вызвать метод <xref:System.String.Substring%2A>.</span><span class="sxs-lookup"><span data-stu-id="88fc8-160">You can then call the <xref:System.String.Substring%2A> method to extract the substring that you want.</span></span> <span data-ttu-id="88fc8-161">К методам сравнения строк можно отнести:</span><span class="sxs-lookup"><span data-stu-id="88fc8-161">The string comparison methods include:</span></span>

- <span data-ttu-id="88fc8-162"><xref:System.String.IndexOf%2A>, возвращающий отсчитываемый от нуля индекс первого появления символа или строки в экземпляре строки.</span><span class="sxs-lookup"><span data-stu-id="88fc8-162"><xref:System.String.IndexOf%2A>, which returns the zero-based index of the first occurrence of a character or string in a string instance.</span></span>

- <span data-ttu-id="88fc8-163"><xref:System.String.IndexOfAny%2A>, возвращающий отсчитываемый от нуля индекс в текущем экземпляре строки первого появления любого символа в массиве символов.</span><span class="sxs-lookup"><span data-stu-id="88fc8-163"><xref:System.String.IndexOfAny%2A>, which returns the zero-based index in the current string instance of the first occurrence of any character in a character array.</span></span>

- <span data-ttu-id="88fc8-164"><xref:System.String.LastIndexOf%2A>, возвращающий отсчитываемый от нуля индекс последнего появления символа или строки в экземпляре строки.</span><span class="sxs-lookup"><span data-stu-id="88fc8-164"><xref:System.String.LastIndexOf%2A>, which returns the zero-based index of the last occurrence of a character or string in a string instance.</span></span>

- <span data-ttu-id="88fc8-165"><xref:System.String.LastIndexOfAny%2A>, возвращающий отсчитываемый от нуля индекс в текущем экземпляре строки последнего вхождения любого символа в массиве символов.</span><span class="sxs-lookup"><span data-stu-id="88fc8-165"><xref:System.String.LastIndexOfAny%2A>, which returns a zero-based index in the current string instance of the last occurrence of any character in a character array.</span></span>

<span data-ttu-id="88fc8-166">В следующем примере метод <xref:System.String.IndexOf%2A> используется для поиска точек в строке.</span><span class="sxs-lookup"><span data-stu-id="88fc8-166">The following example uses the <xref:System.String.IndexOf%2A> method to find the periods in a string.</span></span> <span data-ttu-id="88fc8-167">После чего в нем используется метод <xref:System.String.Substring%2A> для возврата полных предложений.</span><span class="sxs-lookup"><span data-stu-id="88fc8-167">It then uses the <xref:System.String.Substring%2A> method to return full sentences.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/indexof.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/indexof.vb" id="1":::

## <a name="see-also"></a><span data-ttu-id="88fc8-168">См. также</span><span class="sxs-lookup"><span data-stu-id="88fc8-168">See also</span></span>

- [<span data-ttu-id="88fc8-169">Базовые операции со строками в .NET</span><span class="sxs-lookup"><span data-stu-id="88fc8-169">Basic string operations in .NET</span></span>](basic-string-operations.md)
- [<span data-ttu-id="88fc8-170">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="88fc8-170">.NET regular expressions</span></span>](regular-expressions.md)
- [<span data-ttu-id="88fc8-171">Анализ строк с помощью String.Split в C#</span><span class="sxs-lookup"><span data-stu-id="88fc8-171">How to parse strings using String.Split in C#</span></span>](../../csharp/how-to/parse-strings-using-split.md)
