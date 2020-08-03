---
title: Практическое руководство. Изменение содержимого строки (руководство по C#)
description: Ознакомьтесь с примерами нескольких методов изменения содержимого строки в C#, возвращающих новый строковый объект.
ms.date: 02/26/2018
helpviewer_keywords:
- strings [C#], modifying
ms.openlocfilehash: ecce8857befc66353deea341d81f8c6e4313b951
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86473972"
---
# <a name="how-to-modify-string-contents-in-c"></a>Практическое руководство. Изменение содержимого строки в C\#

В этой статье демонстрируется несколько способов получения `string` путем изменения существующего объекта `string`. Все показанные методы возвращают результат изменений как новый объект `string`. Чтобы показать, что исходная и измененная строки являются отдельными экземплярами, в этих примерах результат сохраняется в новой переменной. При выполнении каждого примера можно изучить исходный `string` и новый, измененный `string`.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

В статье приводится несколько методов. Вы можете заменять существующий текст. Вы можете искать шаблоны и заменять соответствующий текст другим. Вы можете рассматривать строку как последовательность символов. Вы также можете использовать удобные методы удаления пробелов. Выберите метод, наиболее подходящий для вашего сценария.

## <a name="replace-text"></a>Замена текста

Следующий код создает новую строку, заменяя существующий текст.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet1":::

В коде выше демонстрируется *неизменяемое* свойство строк. В примере видно, что исходная строка `source` не изменяется. Метод <xref:System.String.Replace%2A?displayProperty=nameWithType> создает новый объект `string`, содержащий изменения.

Метод <xref:System.String.Replace%2A> может заменять строки или отдельные символы. В обоих случаях заменяется каждое вхождение искомого текста.  В следующем примере все символы ' ' заменяются на '\_':

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet2":::

Исходная строка не изменяется. Возвращается новая строка с заменой.

## <a name="trim-white-space"></a>Усечение пробелов

Используйте методы <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType> и <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> для удаления всех начальных или конечных пробелов.  В приведенном ниже коде показан пример каждого метода. Исходная строка не изменяется. Эти методы возвращают новую строку с измененным содержимым.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet3":::

## <a name="remove-text"></a>Удаление текста

Вы можете удалять из строки текст с помощью метода <xref:System.String.Remove%2A?displayProperty=nameWithType>. Этот метод удаляет определенное число символов, начиная с указанного индекса. В следующем примере показано, как использовать <xref:System.String.IndexOf%2A?displayProperty=nameWithType> с <xref:System.String.Remove%2A> для удаления текста из строки:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet4":::

## <a name="replace-matching-patterns"></a>Замена совпадающих шаблонов

Используйте [регулярные выражения](../../standard/base-types/regular-expressions.md) для замены текста, соответствующего шаблонам, на новый текст, который может быть определен шаблоном. В следующем примере используется класс <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> для поиска шаблона в исходной строке и замены его с правильным регистром. Метод <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> принимает в качестве одного из аргументов функцию, которая предоставляет логику замены. В примере эта функция (`LocalReplaceMatchCase`) является **локальной функцией** и объявляется внутри демонстрируемого метода. `LocalReplaceMatchCase` использует класс <xref:System.Text.StringBuilder?displayProperty=nameWithType>, чтобы создать замещающую строку с правильным регистром.

Регулярные выражения наиболее эффективны при поиске и замене текста, который соответствует шаблону, а не известного текста. Дополнительные сведения см. в [практическом руководстве по поиску строк](search-strings.md). Шаблон поиска "the\s" ищет слово "the", за которым следует пробел. Эта часть шаблона гарантирует пропуск слова "there" в исходной строке. Дополнительные сведения об элементах языка регулярных выражений см. в разделе [Элементы языка регулярных выражений — краткий справочник](../../standard/base-types/regular-expression-language-quick-reference.md).

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet5":::

Метод <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> возвращает неизменяемую строку с содержимым в объекте <xref:System.Text.StringBuilder>.

## <a name="modifying-individual-characters"></a>Изменение отдельных символов

Вы можете создать из строки массив символов, изменить содержимое массива, а затем создать из измененного содержимого новую строку.

В примере ниже показано, как заменить набор символов в строке. Сначала используется метод <xref:System.String.ToCharArray?displayProperty=nameWithType> для создания массива символов. Для поиска начального индекса слова "fox" используется метод <xref:System.String.IndexOf%2A>. Следующие три символа заменяются другим словом. Наконец, из обновленного массива символов создается новая строка.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet6":::

## <a name="programmatically-build-up-string-content"></a>Программная сборка содержимого строки

Поскольку строки являются неизменяемыми, в предыдущих примерах создаются временные строки или массивы символов. В высокопроизводительных сценариях, возможно, будет целесообразным избежать этих распределений куч. .NET Core предоставляет метод <xref:System.String.Create%2A?displayProperty=nameWithType>, позволяющий программно заполнять символьное содержимое строки с помощью обратного вызова, избегая промежуточного распределения строк.

:::code language="csharp" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet7":::

Вы можете изменить строку в фиксированном блоке с использованием ненадежного кода, но **крайне** не рекомендует изменять содержимое строки после ее создания. Такая попытка приведет к непредсказуемым последствиям. Например, если кто-то развернет строку, имеющую то же содержимое, что и ваша строка, он получит копию вашей строки и не будет рассчитывать на то, что вы изменяете его строку.

## <a name="see-also"></a>См. также

- [Регулярные выражения в .NET Framework](../../standard/base-types/regular-expressions.md)
- [Элементы языка регулярных выражений — краткий справочник](../../standard/base-types/regular-expression-language-quick-reference.md)
