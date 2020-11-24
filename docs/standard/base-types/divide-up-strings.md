---
title: Разделение строк на подстроки
description: Узнайте о различных методах для извлечения частей строки, в том числе о String.Split, регулярных выражениях и String.Substring.
ms.date: 10/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], breaking up
ms.openlocfilehash: b753476b7d8e5808fdcacc6f28bd1de5f8b232bb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829653"
---
# <a name="extract-substrings-from-a-string"></a>Извлечение подстрок из строки

В этой статье рассматриваются различные методы извлечения частей строки.

- Используйте [метод Split](#stringsplit-method), если нужные подстроки разделены символом-разделителем (или символами).
- [Регулярные выражения](#regular-expressions) удобно использовать, когда строка соответствует фиксированному шаблону.
- Используйте сочетание [методов IndexOf и Substring](#stringindexof-and-stringsubstring-methods), если не хотите извлекать *все* подстроки из строки.

## <a name="stringsplit-method"></a>Метод String.Split

<xref:System.String.Split%2A?displayProperty=nameWithType> предоставляет несколько перегрузок, которые позволяют разбить строку на группу подстрок, основанных на одном или нескольких указанных символах-разделителях. Вы можете ограничить общее число подстрок в окончательном результате, обрезав пробелы в подстроках или исключив пустые подстроки.

Ниже показаны три различные перегрузки `String.Split()`. Первый пример вызывает перегрузку <xref:System.String.Split(System.Char[])> без передачи знаков разделения. Если не указать символы-разделители, `String.Split()` будет использовать для разделения строки разделители по умолчанию, которые являются пробелами.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#1)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="1":::

Как видите, символы-точки (`.`) содержатся в двух подстроках. Если вы хотите исключить символы-точки, добавьте символ-точку как дополнительный символ разделителя. В следующем примере показано, как это сделать.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#2)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="2":::

Точки исчезли из подстрок, однако теперь появились две дополнительные пустые подстроки. Пустые подстроки представляют подстроку между словом и точкой после него. Чтобы исключить из результирующего массива пустые подстроки, вызовите перегрузку <xref:System.String.Split(System.Char[],System.StringSplitOptions)> и укажите <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> для параметра `options`.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#3)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="3":::

## <a name="regular-expressions"></a>Регулярные выражения

Если строка соответствует фиксированному шаблону, используйте регулярное выражение для извлечения и обработки ее элементов. Например, если строки имеют форму "*номер* *операнд* *номер*", тогда для извлечения и обработки элементов строки можно использовать [регулярное выражение](regular-expressions.md). Пример:

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="1":::

Шаблон регулярного выражения `(\d+)\s+([-+*/])\s+(\d+)` определяется следующим образом:

|Шаблон|Описание|
|-------------|-----------------|
|`(\d+)`|Совпадение с одной или несколькими десятичными цифрами. Это первая группа записи.|
|`\s+`|Совпадение с одним или несколькими пробелами.|
|`([-+*/])`|Совпадение со знаком арифметического оператора (+, -, *, или /). Это вторая группа записи.|
|`\s+`|Совпадение с одним или несколькими пробелами.|
|`(\d+)`|Совпадение с одной или несколькими десятичными цифрами. Это третья группа записи.|

Вы также можете использовать регулярное выражение для извлечения подстрок из строки на основе шаблона, а не фиксированного набора символов. Это распространенный сценарий, если происходит одно из следующих условий:

- Один или несколько символов-разделителей не *всегда* служат разделителями в экземпляре <xref:System.String>.

- Последовательность и количество символов-разделителей являются изменяемыми или неизвестными.

Например, метод <xref:System.String.Split%2A> нельзя использовать для разделения следующей строки, поскольку число символов `\n` (новая строка) является изменяемым и они не всегда являются разделителями.

```text
[This is captured\ntext.]\n\n[\n[This is more captured text.]\n]
\n[Some more captured text:\n   Option1\n   Option2][Terse text.]
```

Регулярное выражение может легко разделить эту строку, как показано ниже.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="2" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="2":::

Шаблон регулярного выражения `\[([^\[\]]+)\]` определяется следующим образом:

|Шаблон|Описание|
|-------------|-----------------|
|`\[`|Совпадение с открывающей скобой.|
|`([^\[\]]+)`|Совпадение с любым символом, который не является открывающей или закрывающей скобкой, один или несколько раз. Это первая группа записи.|
|`\]`|Совпадение с закрывающей скобкой.|

Метод <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> практически идентичен методу <xref:System.String.Split%2A?displayProperty=nameWithType>, за исключением того, что он разделяет строку на основе шаблона регулярного выражения, а не фиксированной кодировки. Например, в следующем примере метод <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> используется для разделения строки, которая содержит подстроки, разделенные с помощью различных сочетаний дефисов и других символов.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="3" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="3":::

Шаблон регулярного выражения `\s-\s?[+*]?\s?-\s` определяется следующим образом:

|Шаблон|Описание|
|-------------|-----------------|
|`\s-`|Совпадение с пробелом, за которым следует дефис.|
|`\s?`|Совпадение с нулем или одним символом пробела.|
|`[+*]?`|Совпадение с нулем или единичное появление символа + или *.|
|`\s?`|Совпадение с нулем или одним символом пробела.|
|`-\s`|Совпадение с дефисом, за которым следует пробел.|

## <a name="stringindexof-and-stringsubstring-methods"></a>Методы String.IndexOf и String.Substring

Если вам нужны все подстроки в строке, можете использовать один из методов сравнения строк, которые возвращают индекс начала сопоставления. Затем для извлечения нужных подстрок можно будет вызвать метод <xref:System.String.Substring%2A>. К методам сравнения строк можно отнести:

- <xref:System.String.IndexOf%2A>, возвращающий отсчитываемый от нуля индекс первого появления символа или строки в экземпляре строки.

- <xref:System.String.IndexOfAny%2A>, возвращающий отсчитываемый от нуля индекс в текущем экземпляре строки первого появления любого символа в массиве символов.

- <xref:System.String.LastIndexOf%2A>, возвращающий отсчитываемый от нуля индекс последнего появления символа или строки в экземпляре строки.

- <xref:System.String.LastIndexOfAny%2A>, возвращающий отсчитываемый от нуля индекс в текущем экземпляре строки последнего вхождения любого символа в массиве символов.

В следующем примере метод <xref:System.String.IndexOf%2A> используется для поиска точек в строке. После чего в нем используется метод <xref:System.String.Substring%2A> для возврата полных предложений.

:::code language="csharp" source="snippets/parse-strings/csharp/indexof.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/indexof.vb" id="1":::

## <a name="see-also"></a>См. также

- [Базовые операции со строками в .NET](basic-string-operations.md)
- [Регулярные выражения .NET](regular-expressions.md)
- [Анализ строк с помощью String.Split в C#](../../csharp/how-to/parse-strings-using-split.md)
