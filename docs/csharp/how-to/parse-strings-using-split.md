---
title: Разделение строк с помощью метода String.Split (руководство по C#)
description: Метод Split возвращает массив строк, разбитых по набору разделителей. Это простой способ извлечения подстрок из строки.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: 5361a3c60905edd19b180c5ddb14064a85f64337
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400504"
---
# <a name="how-to-separate-strings-using-stringsplit-in-c"></a>Разделение строк с помощью метода String.Split на C\#

Метод <xref:System.String.Split%2A?displayProperty=nameWithType> создает массив подстрок, разбивая входную строку по одному или нескольким разделителям. Этот метод зачастую является самым простым способом разделить строку по границам слов. Он также используется для разбиения строк по другим конкретным символам или строкам.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Следующий код разбивает обычную фразу на массив строк для каждого слова.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet1":::

Каждый экземпляр знака разделения создает значение в возвращаемом массиве. Последовательные знаки разделения создают пустую строку в виде значения в возвращаемом массиве. В следующем примере показано создание пустой строки с использованием символа пробела в качестве разделителя.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet2":::

Такое поведение упрощает работу с такими форматами, как файл данных с разделителями-запятыми (CSV), которые представляют табличные данные. Идущие подряд запятые представляют пустой столбец.

Чтобы исключить из возвращаемого массива все пустые строки, можно передать необязательный параметр <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType>. Для более сложной обработки возвращенной коллекции можно использовать [LINQ](../programming-guide/concepts/linq/index.md), чтобы управлять результирующей последовательностью.

<xref:System.String.Split%2A?displayProperty=nameWithType> может использовать несколько знаков разделения.
В приведенном ниже примере в качестве знаков разделения используются пробелы, запятые, точки, двоеточия и символы табуляции, которые передаются в <xref:System.String.Split%2A> в массиве.
Цикл в конце кода отображает каждое из слов в возвращенном массиве.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet3":::

Последовательные экземпляры любого разделителя создают пустую строку в выходном массиве:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet4":::

Метод <xref:System.String.Split%2A?displayProperty=nameWithType> может принимать массив строк (в этом случае в качестве разделителей при анализе целевой строки используются последовательности символов, а не отдельные символы).

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet5":::

## <a name="see-also"></a>См. также

- [Извлечение элементов из строки](../../standard/base-types/divide-up-strings.md)
- [Руководство по программированию на C#](../programming-guide/index.md)
- [Строки](../programming-guide/strings/index.md)
- [Регулярные выражения .NET](../../standard/base-types/regular-expressions.md)
