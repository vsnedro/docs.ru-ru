---
title: Изменения в поведении при сравнении строк в .NET 5+
description: Узнайте больше об изменениях в поведении при сравнении строк в .NET 5 и более поздних версий в Windows.
ms.date: 11/04/2020
ms.openlocfilehash: fa1a1d12f45e5b41877a674d7b8747bb2b2f9658
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734235"
---
# <a name="behavior-changes-when-comparing-strings-on-net-5"></a>Изменения в поведении при сравнении строк в .NET 5+

В .NET 5.0 введено изменение поведения среды, и теперь API глобализации используют на всех поддерживаемых платформах [ICU по умолчанию](../../core/compatibility/globalization/5.0/icu-globalization-api.md). Это отход от более ранних версий .NET Core и от .NET Framework, которые используют функциональные возможности многоязыковой поддержки (NLS) операционной системы при работе в Windows. Дополнительные сведения об этих изменениях, включая параметры совместимости, которые могут отменять изменение поведения, см. в статье [Глобализация .NET и ICU](../globalization-localization/globalization-icu.md).

## <a name="reason-for-change"></a>Причина изменения

Это изменение введено для унификации поведения глобализации .NET во всех поддерживаемых операционных системах. Благодаря ему приложения смогут объединять собственные библиотеки глобализации и не зависеть от встроенных библиотек операционных систем. Дополнительные сведения см. в статье [Уведомления о критических изменениях](../../core/compatibility/globalization/5.0/icu-globalization-api.md).

## <a name="behavioral-differences"></a>Различия в поведении

Если вы используете такие функции, как `string.IndexOf(string)`, не вызывая перегрузку, которая принимает аргумент <xref:System.StringComparison>, вместо *порядкового* поиска вы можете непреднамеренно принять зависимость от поведения, на которое влияют язык и региональные параметры. Поскольку NLS и ICU реализуют в лингвистических функциях сравнения другую логику, то результаты таких методов, как `string.IndexOf(string)`, могут возвращать непредвиденные значения.

Такое проявление возможно даже в процессах, для которых активность средств глобализации не всегда ожидаема. Например, следующий код может предоставить не тот ответ в зависимости от текущей среды выполнения.

```cs
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);

// The snippet prints:
//
// '6' when running on .NET Framework (Windows)
// '6' when running on .NET Core 2.x - 3.x (Windows)
// '-1' when running on .NET 5 (Windows)
// '-1' when running on .NET Core 2.x - 3.x or .NET 5 (non-Windows)
// '6' when running on .NET Core 2.x or .NET 5 (in invariant mode)
```

## <a name="guard-against-unexpected-behavior"></a>Предотвращение непредвиденного поведения

В этом разделе приводятся два варианта решения вопросов касательно непредвиденных изменений поведения в .NET 5.0.

### <a name="enable-code-analyzers"></a>Включение анализаторов кода

[Анализаторы кода](../../fundamentals/code-analysis/overview.md) могут обнаруживать места вызовов с ошибками. Для защиты от непредвиденного поведения мы рекомендуем установить [для вашего проекта пакет NuGet __Microsoft.CodeAnalysis.FxCopAnalyzers__](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/). Пакет включает правила анализа кода [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md) и [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md), благодаря которым вы сможете отмечать код, в котором вместо порядкового сравнения непреднамеренно использовалась лингвистическая функция сравнения.

Пример:

```cs
//
// Potentially incorrect code - answer might vary based on locale.
//
string s = GetString();
// Produces analyzer warning CA1307.
int idx = s.IndexOf(",");
Console.WriteLine(idx);

//
// Corrected code - matches the literal substring ",".
//
string s = GetString();
int idx = s.IndexOf(",", StringComparison.Ordinal);
Console.WriteLine(idx);

//
// Corrected code (alternative) - searches for the literal ',' character.
//
string s = GetString();
int idx = s.IndexOf(',');
Console.WriteLine(idx);
```

Аналогичным образом укажите явный компаратор при создании отсортированной коллекции строк или при сортировке существующей коллекции строк.

```cs
//
// Potentially incorrect code - behavior might vary based on locale.
//
SortedSet<string> mySet = new SortedSet<string>();
List<string> list = GetListOfStrings();
list.Sort();

//
// Corrected code - uses ordinal sorting; doesn't vary by locale.
//
SortedSet<string> mySet = new SortedSet<string>(StringComparer.Ordinal);
List<string> list = GetListOfStrings();
list.Sort(StringComparer.Ordinal);
```

Дополнительные сведения об этих правилах анализатора кода, в том числе о том, когда необходимо добавлять эти правила в собственную базу кода, см. в следующих статьях:

* [CA1307. Используйте StringComparison, чтобы ясно указать намерение.](../../fundamentals/code-analysis/quality-rules/ca1307.md)
* [CA1309. Используйте порядковый параметр StringComparison](../../fundamentals/code-analysis/quality-rules/ca1309.md)

### <a name="revert-back-to-nls-behaviors"></a>Возврат к поведению NLS

Чтобы восстановить для приложения .NET 5 прежнее поведение NLS при работе в Windows, выполните действия, описанные в статье [Глобализация .NET и ICU](../globalization-localization/globalization-icu.md). Этот переключатель совместимости следует установить на уровне приложения. Индивидуальные библиотеки не могут перенимать это поведение или отказываться от него.

> [!TIP]
> Мы настоятельно рекомендуем включить правила анализа кода [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md) и [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md) для очистки кода и обнаружения скрытых ошибок. Дополнительные сведения см. в разделе [Включение анализаторов кода](#enable-code-analyzers).

## <a name="affected-apis"></a>Затронутые API

Благодаря изменениям в .NET 5.0 вы не будете сталкиваться с проблемой с непредвиденным поведением в большинстве приложений .NET. Однако, учитывая количество затронутых API, а также их важность для широкой экосистемы .NET, следует обращать внимание на возможное непредвиденное поведение в .NET 5.0 или выявлять имеющиеся скрытые ошибки в приложении.

В число затронутых API входят:

- <xref:System.String.Compare%2A?displayProperty=fullName>
- <xref:System.String.EndsWith%2A?displayProperty=fullName>
- <xref:System.String.IndexOf%2A?displayProperty=fullName>
- <xref:System.String.StartsWith%2A?displayProperty=fullName>
- <xref:System.String.ToLower%2A?displayProperty=fullName>
- <xref:System.String.ToLowerInvariant%2A?displayProperty=fullName>
- <xref:System.String.ToUpper%2A?displayProperty=fullName>
- <xref:System.String.ToUpperInvariant%2A?displayProperty=fullName>
- <xref:System.Globalization.TextInfo?displayProperty=fullName> (большинство элементов)
- <xref:System.Globalization.CompareInfo?displayProperty=fullName> (большинство элементов)
- <xref:System.Array.Sort%2A?displayProperty=fullName> (при сортировке массивов строк)
- <xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (если элементы списка являются строками)
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (если ключи являются строками)
- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (если ключи являются строками)
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (если набор содержит строки)

> [!NOTE]
> Это неполный список затронутых API.

Вышеперечисленные API применяют *лингвистический* поиск и сравнение строк, используя по умолчанию текущие [язык и региональные параметры](xref:System.Threading.Thread.CurrentCulture) потока. Различия между *лингвистическим* и *порядковым* поиском и сравнением описаны в разделе [Противопоставление методов порядкового и лингвистического поиска и сравнения](#ordinal-vs-linguistic-search-and-comparison).

Поскольку ICU реализует лингвистические сравнения строк иначе, чем NLS, приложения Windows, обновленные с более ранней версии .NET Core или .NET Framework до .NET 5.0, вызывающие один из затронутых API, могут работать с различным поведением.

### <a name="exceptions"></a>Исключения

* Если API принимает явный параметр `StringComparison` или `CultureInfo`, этот параметр переопределяет поведение API по умолчанию.
* Элементы `System.String`, в которых параметром является тип `char` (например, <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>), используют порядковый поиск, если вызывающий объект не передает явный аргумент `StringComparison`, указывающий на `CurrentCulture[IgnoreCase]` или `InvariantCulture[IgnoreCase]`.

Более подробный анализ стандартного поведения для каждого API <xref:System.String> см. в разделе [Стандартные типы поиска и сравнения](#default-search-and-comparison-types).

## <a name="ordinal-vs-linguistic-search-and-comparison"></a>Противопоставление методов порядкового и лингвистического поиска и сравнения

*Порядковый* (или *не лингвистический*) поиск и сравнение разбивает строку на отдельные элементы `char` и выполняет поиск или сравнение по каждому типу char. Например, строки `"dog"` и `"dog"` в функции сравнения `Ordinal` определяются как *равные*, поскольку обе состоят из одной и той же последовательности символов char. Однако сравнение строк `"dog"` и `"Dog"` приводит к значению *не равно* в функции сравнения `Ordinal`, поскольку последовательности символов char в этих строках отличаются. Это значит, что кодовая точка `U+0044` прописной `'D'` появляется до кодовой точки `U+0064` нижнего регистра `'d'`, что приводит к сортировке `"dog"` перед `"Dog"`.

Функция сравнения `OrdinalIgnoreCase` по-прежнему работает с каждым символом char, однако устраняет различия в регистрах при выполнении операции. В функции сравнения `OrdinalIgnoreCase` пары символов char `'d'` и `'D'` будут определены как *равные*, как и пары символов char `'á'` и `'Á'`. Однако символ char без диакритического знака `'a'` и символ char с диакритическим знаком `'á'` при сравнении определяются как *не равно*.

Некоторые примеры приведены в следующей таблице.

| Строка 1 | Строка 2 | Сравнение `Ordinal` | Сравнение `OrdinalIgnoreCase` |
|---|---|---|---|
| `"dog"` | `"dog"` | equal | equal |
| `"dog"` | `"Dog"` | не равно | equal |
| `"resume"` | `"Resume"` | не равно | equal |
| `"resume"` | `"résumé"` | не равно | не равно |

В Юникоде строки также могут иметь несколько различных представлений в памяти. Например, e с акутом (é) можно представить двумя способами:

* Одиночный литерал `'é'` (также пишется как `'\u00E9'`).
* Литерал без диакритических знаков `'e'`, за которым следует символ объединения диакритических знаков `'\u0301'`.

Это означает, что при отображении следующие _четыре_ строки будут представлены как `"résumé"`, даже если их составные части отличаются. В строках используется сочетание литералов `'é'` или литералов без диакритических знаков `'e'` с модификатором объединения диакритических знаков `'\u0301'`.

* `"r\u00E9sum\u00E9"`
* `"r\u00E9sume\u0301"`
* `"re\u0301sum\u00E9"`
* `"re\u0301sume\u0301"`

При использовании порядковой функции сравнения ни одна из этих строк не будет представлена как равная другой. Это связано с тем, что все они содержат разные базовые последовательности символов char, даже если при отображении на экране выглядят одинаково.

При выполнении операции `string.IndexOf(..., StringComparison.Ordinal)` среда выполнения ищет точную совпадающую подстроку. Результаты выглядят следующим образом.

```cs
Console.WriteLine("resume".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("resume".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
```

На поисковые и сравнительные подпрограммы язык и региональные параметры текущего потока не влияют.

Подпрограммы для *лингвистического* поиска и сравнения разбивают строку на *элементы параметров сортировки* и выполняют поиск или сравнение этих элементов. Не обязательно сопоставлять символы строк с составными элементами параметров сортировки 1:1. Например, строка длиной 2 символа может состоять только из одного элемента параметров сортировки. При сравнении двух строк с учетом лингвистического сравнения функция сравнения проверяет, имеют ли два элемента параметров сортировки одинаковое семантическое значение, даже если литеральные символы строки различны.

Рассмотрим строку `"résumé"` и ее четыре различные интерпретации еще раз. В следующей таблице показаны все интерпретации, разделенные на элементы параметров сортировки.

| Строка | Как элементы параметров сортировки |
|---|---|
| `"r\u00E9sum\u00E9"` | `"r" + "\u00E9" + "s" + "u" + "m" + "\u00E9"` |
| `"r\u00E9sume\u0301"` | `"r" + "\u00E9" + "s" + "u" + "m" + "e\u0301"` |
| `"re\u0301sum\u00E9"` | `"r" + "e\u0301" + "s" + "u" + "m" + "\u00E9"` |
| `"re\u0301sume\u0301"` | `"r" + "e\u00E9" + "s" + "u" + "m" + "e\u0301"` |

Элемент параметров сортировки частично соответствует тому, что читатели представляют, думая об одном символе или кластере символов. Он концептуально похож на [кластер графем](character-encoding-introduction.md#grapheme-clusters), однако охватывает более крупные группировки.

В лингвистической функции сравнения точные совпадения не требуются. Элементы параметров сортировки сравниваются на основе их семантического значения. Например, лингвистическая функция сравнения анализирует подстроки `"\u00E9"` и `"e\u0301"` как равные, поскольку они обе семантически означают "строчная буква e с модификатором знака акута". Это позволяет методу `IndexOf` сопоставлять подстроку `"e\u0301"` в более длинной строке, содержащей семантически эквивалентную подстроку `"\u00E9"`, как показано в следующем примере кода.

```cs
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e")); // prints '-1' (not found)
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e\u00E9")); // prints '1'
Console.WriteLine("\u00E9".IndexOf("e\u00E9")); // prints '0'
```

Как следствие, при лингвистическом сравнении две строки разной длины могут быть представлены как равные. Вызывающие объекты не должны следовать логике особых случаев, которая в таких сценариях учитывает длину строки.

Подпрограммы поиска и сравнения с учетом *языка и региональных параметров* представляют собой специальную форму подпрограмм лингвистического поиска и сравнения. В функции сравнения, учитывающей язык и региональные параметры, понятие элемента параметров сортировки расширено до включения сведений, относящихся к заданному языку и региональным параметрам.

Например, [в венгерском алфавите](https://en.wikipedia.org/wiki/Hungarian_alphabet), когда два символа \<dz\> следуют один за другим, они считаются собственными уникальными буквами, отличающимися от \<d\> или \<z\>. Это означает, что если в строке отображается \<dz\>, функция сравнения с поддержкой венгерского языка и региональных параметров рассматривает этот символ как отдельный элемент параметров сортировки.

| Строка | Как элементы параметров сортировки | Комментарии |
|---|---|---|
| `"endz"` | `"e" + "n" + "d" + "z"` | (использование стандартной лингвистической функции сравнения) |
| `"endz"` | `"e" + "n" + "dz"` | (использование функции сравнения с поддержкой венгерского языка) |

Это значит, что при использовании функции сравнения с поддержкой венгерского языка и региональных параметров строка `"endz"` *не* заканчивается подстрокой `"z"`, поскольку <\dz\> и <\z\> считаются элементами сортировки с другим семантическим значением.

```cs
// Set thread culture to Hungarian
CultureInfo.CurrentCulture = CultureInfo.GetCultureInfo("hu-HU");
Console.WriteLine("endz".EndsWith("z")); // Prints 'False'

// Set thread culture to invariant culture
CultureInfo.CurrentCulture = CultureInfo.InvariantCulture;
Console.WriteLine("endz".EndsWith("z")); // Prints 'True'
```

> [!NOTE]
>
> - Поведение. Лингвистические функции сравнения и функции сравнения с учетом языка и региональных параметров могут иногда корректировать поведение. ICU и более старые функции Windows NLS обновляются с учетом изменений в мировых языках. Дополнительные сведения см. в записи блога [Смешивание локальных данных (язык и региональные параметры)](/archive/blogs/shawnste/locale-culture-data-churn). Поведение *порядковой* функции сравнения не изменится, поскольку она выполняет точную операцию поиска и сравнения по битам. Однако поведение функции сравнения *OrdinalIgnoreCase* может изменяться по мере увеличения Юникода для охвата большего количества наборов символов и исправления пропусков в существующих данных регистра.
> - Использование. Функции сравнения `StringComparison.InvariantCulture` и `StringComparison.InvariantCultureIgnoreCase` являются лингвистическими функциями сравнения, которые не поддерживают языки и региональные параметры. Это значит, что эти функции сравнения настроены так, что диакритический знак é может иметь несколько возможных базовых интерпретаций и все эти интерпретации должны обрабатываться одинаково. Однако лингвистические функции сравнения без поддержки языков и региональных параметров не будут использовать специальную обработку для символа \<dz\> как отличного от \<d\> или \<z\>, как показано выше. Они также не поддерживают специальные символы, такие как немецкий Eszett (ß).

.NET также предлагает *инвариантный режим глобализации*. Этот режим отключает пути кода, которые работают с лингвистическими подпрограммами поиска и сравнения. В этом режиме все операции используют поведение *Ordinal* или *OrdinalIgnoreCase*, независимо от того, какой из аргументов, `CultureInfo` или `StringComparison`, предоставляется вызывающим объектом. Дополнительные сведения см. в статьях [Параметры конфигурации времени выполнения для глобализации](../../core/run-time-config/globalization.md) и [Инвариантный режим глобализации в .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

Дополнительные сведения см. в статье [Рекомендации по сравнению строк в .NET](best-practices-strings.md).

## <a name="security-implications"></a>Последствия для безопасности

Если ваше приложение использует для фильтрации затронутый API, рекомендуется включить правила для анализа кода CA1307 и CA1309, чтобы находить места непреднамеренного использования лингвистического поиска вместо порядкового. Приведенные ниже шаблоны кода могут быть подвержены взломам системы безопасности.

```cs
//
// THIS SAMPLE CODE IS INCORRECT.
// DO NOT USE IT IN PRODUCTION.
//
public bool ContainsHtmlSensitiveCharacters(string input)
{
    if (input.IndexOf("<") >= 0) { return true; }
    if (input.IndexOf("&") >= 0) { return true; }
    return false;
}
```

Поскольку метод `string.IndexOf(string)` использует лингвистический поиск по умолчанию, строка может содержать литерал `'<'` или `'&'`, а подпрограммы `string.IndexOf(string)` возвращать `-1`, указывая на то, что подстроку поиска не найдено. Правила анализа кода CA1307 и CA1309 помечают такие точки вызова и предупреждают разработчика о потенциальных проблемах.

## <a name="default-search-and-comparison-types"></a>Стандартные типы поиска и сравнения

В следующей таблице перечислены стандартные типы поиска и сравнения для различных API string и string-like. Если вызывающий объект предоставляет явный параметр `CultureInfo` или `StringComparison`, этот параметр будет учитываться как приоритетный по отношению к параметрам по умолчанию.

| API | Поведение по умолчанию | Комментарии |
|---|---|---|
| `string.Compare` | CurrentCulture | |
| `string.CompareTo` | CurrentCulture | |
| `string.Contains` | Порядковый номер | |
| `string.EndsWith` | Порядковый номер | (когда первый параметр — `char`) |
| `string.EndsWith` | CurrentCulture | (когда первый параметр — `string`) |
| `string.Equals` | Порядковый номер | |
| `string.GetHashCode` | Порядковый номер | |
| `string.IndexOf` | Порядковый номер | (когда первый параметр — `char`) |
| `string.IndexOf` | CurrentCulture | (когда первый параметр — `string`) |
| `string.IndexOfAny` | Порядковый номер | |
| `string.LastIndexOf` | Порядковый номер | (когда первый параметр — `char`) |
| `string.LastIndexOf` | CurrentCulture | (когда первый параметр — `string`) |
| `string.LastIndexOfAny` | Порядковый номер | |
| `string.Replace` | Порядковый номер | |
| `string.Split` | Порядковый номер | |
| `string.StartsWith` | Порядковый номер | (когда первый параметр — `char`) |
| `string.StartsWith` | CurrentCulture | (когда первый параметр — `string`) |
| `string.ToLower` | CurrentCulture | |
| `string.ToLowerInvariant` | InvariantCulture | |
| `string.ToUpper` | CurrentCulture | |
| `string.ToUpperInvariant` | InvariantCulture | |
| `string.Trim` | Порядковый номер | |
| `string.TrimEnd` | Порядковый номер | |
| `string.TrimStart` | Порядковый номер | |
| `string == string` | Порядковый номер | |
| `string != string` | Порядковый номер | |

В отличие от API `string`, все API `MemoryExtensions` по умолчанию выполняют *порядковый* поиск и сравнение со следующими исключениями.

| API | Поведение по умолчанию | Комментарии |
|---|---|---|
| `MemoryExtensions.ToLower` | CurrentCulture | (при передаче нулевого аргумента `CultureInfo`) |
| `MemoryExtensions.ToLowerInvariant` | InvariantCulture | |
| `MemoryExtensions.ToUpper` | CurrentCulture | (при передаче нулевого аргумента `CultureInfo`) |
| `MemoryExtensions.ToUpperInvariant` | InvariantCulture | |

Следствием является то, что при преобразовании кода от использования `string` к использованию `ReadOnlySpan<char>` изменения в поведении могут быть сделаны непреднамеренно. Далее приведен пример.

```cs
string str = GetString();
if (str.StartsWith("Hello")) { /* do something */ } // this is a CULTURE-AWARE (linguistic) comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello")) { /* do something */ } // this is an ORDINAL (non-linguistic) comparison
```

Чтобы устранить это явление, рекомендуется передавать явный параметр `StringComparison` в эти API. Для этого можно использовать правила анализа кода CA1307 и CA1309.

```cs
string str = GetString();
if (str.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison
```

## <a name="see-also"></a>См. также

- [Критические изменения в области глобализации](../../core/compatibility/globalization.md)
- [Рекомендации по сравнению строк в .NET](best-practices-strings.md)
- [Сравнение строк в C#](../../csharp/how-to/compare-strings.md)
- [Глобализация .NET и ICU](../globalization-localization/globalization-icu.md)
- [Сравнение порядковых операций со строками и операций, учитывающих язык и региональные параметры](/dotnet/api/system.string#ordinal-vs-culture-sensitive-operations)
- [Обзор анализа исходного кода .NET](../../fundamentals/code-analysis/overview.md)
