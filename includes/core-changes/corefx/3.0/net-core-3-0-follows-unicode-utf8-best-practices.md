---
ms.openlocfilehash: 298cb441bf9fe7daddb30c85f9d7366dc972628c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032141"
---
### <a name="replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines"></a>Замена неправильно сформированных последовательностей байтов в кодировке UTF-8 в соответствии с правилами Юникода

Если в процессе кодирования байтов в символы класс <xref:System.Text.UTF8Encoding> обнаруживает некорректно сформированную последовательность байтов UTF-8, в выходной строке она заменяется символом � (СИМВОЛ ЗАМЕНЫ U+FFFD). В .NET Core 3.0, в отличие от предыдущих версий .NET Core и .NET Framework, применяются рекомендации по Юникоду для таких замен при операциях перекодирования.

Это лишь часть больших усилий улучшить обработку данных в формате UTF-8 в .NET, включая новые типы <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> и <xref:System.Text.Rune?displayProperty=nameWithType>. Для типа <xref:System.Text.UTF8Encoding> предоставлен улучшенный механизм обработки ошибок, чтобы его выходные данные соответствовали новым типам.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Core 3.0, при перекодировании байтов в символы класс <xref:System.Text.UTF8Encoding> выполняет подстановку символов на основе рекомендаций по Юникоду. Используемый механизм подстановки описан в [документе по стандарту "Юникод" версии 12.0, раздел 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) с заголовком _U+FFFD Substitution of Maximal Subparts_ (Замена наибольшей части неправильной последовательности символом U+FFFD).

Такой подход _применяется_ только в том случае, если входная последовательность байтов содержит некорректные данные в кодировке UTF-8. Кроме того, если экземпляр <xref:System.Text.UTF8Encoding> был создан с помощью `throwOnInvalidBytes: true`, экземпляр `UTF8Encoding` будет и дальше выдавать исключение при недопустимых входных данных, а не выполнять замену символом U+FFFD. Дополнительные сведения о конструкторе `UTF8Encoding` см. в статье <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>.

В следующей таблице показано влияние этого изменения на примере недопустимых 3-байтовых входных данных.

| Некорректно сформированные 3-байтовые входные данные | Выходные данные в версиях до .NET Core 3.0          | Выходные данные в .NET Core 3.0 и более поздних версиях        |
|-------------------------|--------------------------------------|-------------------------------------------|
| `[ ED A0 90 ]`          | `[ FFFD FFFD ]` (выходные данные в виде двухзначного кода) | `[ FFFD FFFD FFFD ]` (выходные данные в виде трехзначного кода) |

Согласно _таблице 3-9_ из PDF-документа по Юникоду, ссылка на который приведена выше, предпочтительным является вариант с выходными данными в виде трехзначного кода.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

От разработчика не требуется никаких действий.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
