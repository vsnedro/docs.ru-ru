---
title: Миграция из Newtonsoft.Json в System.Text.Json — .NET
author: tdykstra
ms.author: tdykstra
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: fbd3c8062892f106ec17d0fef86d5ad7f1207d20
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303482"
---
# <a name="how-to-migrate-from-no-locnewtonsoftjson-to-no-locsystemtextjson"></a>Миграция из Newtonsoft.Json в System.Text.Json

В этой статье описывается миграция из [Newtonsoft.Json](https://www.newtonsoft.com/json) в <xref:System.Text.Json>.

Пространство имен `System.Text.Json` предоставляет функциональные возможности для сериализации в нотацию объектов JavaScript (JSON) и десериализации объектов из этой нотации. Библиотека `System.Text.Json` входит в состав общей платформы [.NET Core 3.0](https://aka.ms/netcore3download). Для других целевых платформ установите пакет NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json). Пакет поддерживает:

* .NET Standard 2.0 и более поздних версий
* .NET Framework 4.7.2 и более поздних версий
* .NET Core 2.0, 2.1 и 2.2

`System.Text.Json` основное внимание уделяет требованиям, предъявляемым к производительности, безопасности и стандартам. У него есть некоторые ключевые отличия в поведении по умолчанию, и он не стремится к равенству функций с `Newtonsoft.Json`. В некоторых сценариях `System.Text.Json` не имеет встроенных функций, но существуют рекомендованные способы обойти проблему. В других сценариях обходные пути нецелесообразны. Если приложение зависит от отсутствующей функции, возможно, следует [сообщить о проблеме](https://github.com/dotnet/runtime/issues/new), чтобы узнать, можно ли добавить поддержку для вашего сценария.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

Большая часть этой статьи посвящена использованию API <xref:System.Text.Json.JsonSerializer>, но также содержит рекомендации по использованию <xref:System.Text.Json.JsonDocument> (который представляет модель DOM), <xref:System.Text.Json.Utf8JsonReader> и типов <xref:System.Text.Json.Utf8JsonWriter>.

## <a name="table-of-differences-between-no-locnewtonsoftjson-and-no-locsystemtextjson"></a>Таблица различий между Newtonsoft.Json и System.Text.Json

В следующей таблице перечислены функции `Newtonsoft.Json` и эквиваленты `System.Text.Json`. Эквиваленты делятся на следующие категории:

* Поддерживается встроенными функциональными возможностями. Для получения подобного поведения в `System.Text.Json` может потребоваться использование атрибута или глобального параметра.
* Не поддерживается, существует обходной путь. В качестве обходных путей можно использовать [пользовательские преобразователи](system-text-json-converters-how-to.md), которые могут не обеспечивать полное равенство с функциями `Newtonsoft.Json`. Для некоторых случаев приведены примеры кода. Если вы используете эти функции `Newtonsoft.Json`, для миграции потребуется внести изменения в объектные модели .NET или другие части кода.
* Не поддерживается, обходной путь нецелесообразен или невозможен. Если вы используете эти функции `Newtonsoft.Json`, миграция будет невозможна без существенных изменений.

| Функция Newtonsoft.Json                               | Эквивалент System.Text.Json |
|-------------------------------------------------------|-----------------------------|
| Десериализация без учета регистра по умолчанию           | ✔️ [Глобальный параметр PropertyNameCaseInsensitive](#case-insensitive-deserialization) |
| Имена свойств в "верблюжьем" стиле                             | ✔️ [Глобальный параметр PropertyNamingPolicy](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) |
| Минимальное экранирование символов                            | ✔️ [Строгое экранирование символов, возможность настройки](#minimal-character-escaping) |
| Глобальный параметр `NullValueHandling.Ignore`             | ✔️ [Глобальный параметр IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) |
| Возможность комментариев                                        | ✔️ [Глобальный параметр ReadCommentHandling](#comments) |
| Возможность конечных запятых                                 | ✔️ [Глобальный параметр AllowTrailingCommas](#trailing-commas) |
| Регистрация пользовательского преобразователя                         | ✔️ [Очередность применения различается](#converter-registration-precedence) |
| По умолчанию отсутствует максимальная глубина                           | ✔️ [Максимальная глубина по умолчанию —64, настраиваемая](#maximum-depth) |
| Поддержка широкого спектра типов                    | ⚠️ [Для некоторых типов требуются пользовательские преобразователи](#types-without-built-in-support) |
| Десериализация строк как чисел                        | ⚠️ [Не поддерживается, существует обходной путь, пример](#quoted-numbers) |
| Десериализация `Dictionary` с ключом, не являющимся строкой          | ⚠️ [Не поддерживается, существует обходной путь, пример](#dictionary-with-non-string-key) |
| Полиморфная сериализация                             | ⚠️ [Не поддерживается, существует обходной путь, пример](#polymorphic-serialization) |
| Полиморфная десериализация                           | ⚠️ [Не поддерживается, существует обходной путь, пример](#polymorphic-deserialization) |
| Десериализация выводимого типа в свойства `object`      | ⚠️ [Не поддерживается, существует обходной путь, пример](#deserialization-of-object-properties) |
| Десериализация литерала JSON `null` в типы значений, не допускающие значения NULL | ⚠️ [Не поддерживается, существует обходной путь, пример](#deserialize-null-to-non-nullable-type) |
| Десериализация в неизменяемые классы и структуры          | ⚠️ [Не поддерживается, существует обходной путь, пример](#deserialize-to-immutable-classes-and-structs) |
| Атрибут `[JsonConstructor]`                         | ⚠️ [Не поддерживается, существует обходной путь, пример](#specify-constructor-to-use) |
| Установка `Required` для атрибута `[JsonProperty]`        | ⚠️ [Не поддерживается, существует обходной путь, пример](#required-properties) |
| Установка `NullValueHandling` для атрибута `[JsonProperty]` | ⚠️ [Не поддерживается, существует обходной путь, пример](#conditionally-ignore-a-property)  |
| Установка `DefaultValueHandling` для атрибута `[JsonProperty]` | ⚠️ [Не поддерживается, существует обходной путь, пример](#conditionally-ignore-a-property)  |
| Глобальный параметр `DefaultValueHandling`                 | ⚠️ [Не поддерживается, существует обходной путь, пример](#conditionally-ignore-a-property) |
| `DefaultContractResolver` для исключения свойств       | ⚠️ [Не поддерживается, существует обходной путь, пример](#conditionally-ignore-a-property) |
| Параметры `DateTimeZoneHandling`, `DateFormatString`   | ⚠️ [Не поддерживается, существует обходной путь, пример](#specify-date-format) |
| Обратные вызовы                                             | ⚠️ [Не поддерживается, существует обходной путь, пример](#callbacks) |
| Поддержка открытых и не открытых полей              | ⚠️ [Не поддерживается, существует обходной путь, пример](#public-and-non-public-fields) |
| Поддержка методов задания и получения для внутренних и закрытых свойств | ⚠️ [Не поддерживается, существует обходной путь, пример](#internal-and-private-property-setters-and-getters) |
| Метод `JsonConvert.PopulateObject`                   | ⚠️ [Не поддерживается, существует обходной путь, пример](#populate-existing-objects) |
| Глобальный параметр `ObjectCreationHandling`               | ⚠️ [Не поддерживается, существует обходной путь, пример](#reuse-rather-than-replace-properties) |
| Добавление в коллекции без методов задания                    | ⚠️ [Не поддерживается, существует обходной путь, пример](#add-to-collections-without-setters) |
| Глобальный параметр `PreserveReferencesHandling`           | ❌ [Не поддерживается](#preserve-object-references-and-handle-loops) |
| Глобальный параметр `ReferenceLoopHandling`                | ❌ [Не поддерживается](#preserve-object-references-and-handle-loops) |
| Поддержка атрибутов `System.Runtime.Serialization` | ❌ [Не поддерживается](#systemruntimeserialization-attributes) |
| Глобальный параметр `MissingMemberHandling`                | ❌ [Не поддерживается](#missingmemberhandling) |
| Возможность имен свойств без кавычек                   | ❌ [Не поддерживается](#json-strings-property-names-and-string-values) |
| Возможность одиночных кавычек вокруг строковых значений              | ❌ [Не поддерживается](#json-strings-property-names-and-string-values) |
| Возможность нестроковых значений JSON для строковых свойств    | ❌ [Не поддерживается](#non-string-values-for-string-properties) |

Это неполный список функций `Newtonsoft.Json`. В список входят многие сценарии, которые были запрошены в [проблемах GitHub](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) или записях [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json). Если вы реализуете обходной путь для одного из перечисленных здесь сценариев, для которого в настоящее время нет примера кода, и если вы хотите поделиться своим решением, нажмите **Эта страница** в разделе **Отзывы** (в нижней части этой страницы). Это позволит создать проблему в репозитории GitHub в этой документации и указать ее в разделе **Отзывы** на этой странице.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-no-locnewtonsoftjson"></a>Различия в поведении JsonSerializer по умолчанию по сравнению с Newtonsoft.Json

<xref:System.Text.Json> по умолчанию является строгим и избегает двусмысленностей со стороны вызывающего объекта, подчеркивая детерминированное поведение. Библиотека преднамеренно разработана таким образом для повышения производительности и безопасности. `Newtonsoft.Json` по умолчанию является гибким. Это фундаментальное различие в проектировании обуславливает многие из следующих различий в поведении по умолчанию.

### <a name="case-insensitive-deserialization"></a>Десериализация без учета регистра

Во время десериализации `Newtonsoft.Json` выполняет сопоставление имени свойства без учета регистра по умолчанию. <xref:System.Text.Json> по умолчанию учитывает регистр, что обеспечивает более высокую производительность, так как соответствие является точным. Сведения о том, как выполнять сопоставление без учета регистра, см. в разделе [Сопоставление свойств без учета регистра](system-text-json-how-to.md#case-insensitive-property-matching).

Если вы используете `System.Text.Json` косвенно с помощью ASP.NET Core, вам не нужно ничего делать для получения поведения, аналогичного `Newtonsoft.Json`. ASP.NET Core задает параметры для [имен свойств в "верблюжьем" стиле](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) и сопоставления без учета регистра при использовании `System.Text.Json`.

### <a name="minimal-character-escaping"></a>Минимальное экранирование символов

Во время сериализации `Newtonsoft.Json` обеспечивает относительную свободу, разрешая символы без экранирования. То есть он не заменяет их на `\uxxxx`, где `xxxx` является кодовой точкой символа. Когда он использует экранирование, он выдает `\` перед символом (например, `"` преобразуется в `\"`). <xref:System.Text.Json> по умолчанию экранирует больше символов, чтобы обеспечить глубокую защиту от межсайтового скриптинга (XSS) или атак с раскрытием информации и делает это с помощью последовательности из шести символов. `System.Text.Json` экранирует все символы, отличные от ASCII, по умолчанию, поэтому вам не нужно ничего делать, если вы используете `StringEscapeHandling.EscapeNonAscii` в `Newtonsoft.Json`. `System.Text.Json` также по умолчанию экранирует символы, учитывающие HTML. Сведения о том, как переопределить поведение `System.Text.Json` по умолчанию, см. в разделе [Настройка кодировки символов](system-text-json-how-to.md#customize-character-encoding).

### <a name="comments"></a>Комментарии

Во время десериализации `Newtonsoft.Json` по умолчанию игнорирует комментарии в JSON. <xref:System.Text.Json> по умолчанию выдает исключения для комментариев, так как спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не включает их. Сведения о том, как разрешить комментарии, см. в разделе [Возможность комментариев и конечных запятых](system-text-json-how-to.md#allow-comments-and-trailing-commas).

### <a name="trailing-commas"></a>Конечные запятые

Во время десериализации `Newtonsoft.Json` по умолчанию игнорирует конечные запятые. Он также игнорирует несколько конечных запятых (например, `[{"Color":"Red"},{"Color":"Green"},,]`). <xref:System.Text.Json> по умолчанию выдает исключения для конечных запятых, так как спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не разрешает их. Сведения о том, как заставить `System.Text.Json` их принять, см. в разделе [Возможность комментариев и конечных запятых](system-text-json-how-to.md#allow-comments-and-trailing-commas). Невозможно разрешить несколько конечных запятых.

### <a name="converter-registration-precedence"></a>Очередность регистрации преобразователей

Очередность регистрации `Newtonsoft.Json` для пользовательских преобразователей выглядит следующим образом.

* Атрибут для свойства
* Атрибут для типа
* Коллекция [преобразователей](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)

Этот порядок означает, что пользовательский преобразователь в коллекции `Converters` переопределяется преобразователем, зарегистрированным путем применения атрибута на уровне типа. Обе эти регистрации переопределяются атрибутом на уровне свойства.

Очередность регистрации <xref:System.Text.Json> для пользовательских преобразователей выглядит иначе:

* Атрибут для свойства
* Коллекция <xref:System.Text.Json.JsonSerializerOptions.Converters>
* Атрибут для типа

Разница заключается в том, что пользовательский преобразователь в коллекции `Converters` переопределяет атрибут на уровне типа. Цель этой очередности заключается в том, чтобы изменения во время выполнения переопределяли варианты во время разработки. Изменить очередность невозможно.

Дополнительные сведения о регистрации пользовательских преобразователей см. в разделе [Регистрация пользовательского преобразователя](system-text-json-converters-how-to.md#register-a-custom-converter).

### <a name="maximum-depth"></a>Максимальная глубина

`Newtonsoft.Json` по умолчанию не имеет максимального предела глубины. Для <xref:System.Text.Json> существует ограничение по умолчанию 64, которое можно настроить, задав <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.

### <a name="json-strings-property-names-and-string-values"></a>Строки JSON (имена свойств и строковые значения)

Во время десериализации `Newtonsoft.Json` принимает имена свойств, заключенные в двойные кавычки, одинарные кавычки или без кавычек. Он принимает строковые значения, заключенные в двойные кавычки или одинарные кавычки. Например, `Newtonsoft.Json` принимает следующий код JSON:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json` принимает имена свойств и строковые значения только в двойных кавычках, так как этот формат требуется спецификацией [RFC 8259](https://tools.ietf.org/html/rfc8259) и является единственным форматом, который считается допустимым JSON.

Значение, заключенное в одинарные кавычки, приводит к исключению [JsonException](xref:System.Text.Json.JsonException) со следующим сообщением:

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Нестроковые значения для строковых свойств

`Newtonsoft.Json` принимает нестроковые значения, например числа или литералы `true` и `false`, для десериализации в свойства строкового типа. Ниже приведен пример JSON, который `Newtonsoft.Json` успешно десериализует в следующий класс:

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

`System.Text.Json` не выполняет десериализацию нестроковых значений в строковые свойства. Нестроковое значение, полученное для строкового поля, приводит к исключению [JsonException](xref:System.Text.Json.JsonException) со следующим сообщением:

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>Сценарии с использованием JsonSerializer, для которых требуются обходные пути

Следующие сценарии не поддерживаются встроенными функциями, но возможны обходные пути. В качестве обходных путей можно использовать [пользовательские преобразователи](system-text-json-converters-how-to.md), которые могут не обеспечивать полное равенство с функциями `Newtonsoft.Json`. Для некоторых случаев приведены примеры кода. Если вы используете эти функции `Newtonsoft.Json`, для миграции потребуется внести изменения в объектные модели .NET или другие части кода.

### <a name="types-without-built-in-support"></a>Типы без встроенной поддержки

<xref:System.Text.Json> не предоставляет встроенную поддержку для следующих типов:

* <xref:System.Data.DataTable> и связанные типы
* Типы F#, такие как [различаемые объединения](../../fsharp/language-reference/discriminated-unions.md), [типы записей](../../fsharp/language-reference/records.md) и [типы анонимных записей](../../fsharp/language-reference/anonymous-records.md).
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple> и связанные с ним универсальные типы

Пользовательские преобразователи можно реализовать для типов, у которых нет встроенной поддержки.

### <a name="quoted-numbers"></a>Заключенные в кавычки числа

`Newtonsoft.Json` может сериализовать или десериализовать числа, представленные строками JSON (заключенные в кавычки). Например, он может принимать `{"DegreesCelsius":"23"}` вместо `{"DegreesCelsius":23}`. Чтобы включить это поведение в <xref:System.Text.Json>, реализуйте пользовательский преобразователь, как показано в следующем примере. Преобразователь обрабатывает свойства, определенные как `long`:

* Он сериализует их как строки JSON.
* Он принимает числа JSON и числа в кавычках при десериализации.

[!code-csharp[](snippets/system-text-json-how-to/csharp/LongToStringConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь, [используя атрибут](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) для отдельных свойств `long` или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

### <a name="dictionary-with-non-string-key"></a>Словарь с ключом, не являющимся строкой

`Newtonsoft.Json` поддерживает коллекции типа `Dictionary<TKey, TValue>`. Встроенная поддержка коллекций словарей в <xref:System.Text.Json> ограничена `Dictionary<string, TValue>`. То есть ключ должен быть строкой.

Для поддержки словаря с целым числом или другим типом в качестве ключа создайте преобразователь, аналогичный примеру в разделе [Как писать пользовательские преобразователи](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).

### <a name="polymorphic-serialization"></a>Полиморфная сериализация

`Newtonsoft.Json` автоматически выполняет полиморфную сериализацию. Сведения о возможностях ограниченной полиморфной сериализации в <xref:System.Text.Json> см. в разделе [Сериализация свойств производных классов](system-text-json-how-to.md#serialize-properties-of-derived-classes).

Описанный обходной путь состоит в определении свойств, которые могут содержать производные классы в качестве типа `object`. Если это невозможно, можно создать преобразователь с методом `Write` для всей иерархии типов наследования, как в примере в разделе [Написание пользовательских преобразователей](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="polymorphic-deserialization"></a>Полиморфная десериализация

`Newtonsoft.Json` имеет параметр `TypeNameHandling`, который добавляет метаданные имени типа в JSON во время сериализации. Он использует метаданные во время десериализации для выполнения полиморфной десериализации. <xref:System.Text.Json> может ограниченно выполнять [полиморфную сериализацию](system-text-json-how-to.md#serialize-properties-of-derived-classes), но не полиморфную десериализацию.

Чтобы обеспечить поддержку полиморфной десериализации, создайте преобразователь, как в примере в разделе [Написание пользовательских преобразователей](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="deserialization-of-object-properties"></a>Десериализация свойств объекта

Когда `Newtonsoft.Json` выполняет десериализацию в <xref:System.Object>, он:

* Выводит типы примитивных значений в полезных данных JSON (кроме `null`) и возвращает хранимые `string`, `long`, `double`, `boolean` или `DateTime` в виде упакованного объекта. *Примитивные значения* — это отдельные значения JSON, такие как число JSON, строка, `true`, `false` или `null`.
* Возвращает `JObject` или `JArray` для сложных значений в полезных данных JSON. *Сложные значения* являются коллекциями пар "ключ-значение" JSON в фигурных скобках (`{}`) или списками значений в квадратных скобках (`[]`). Свойства и значения в фигурных или квадратных скобках могут иметь дополнительные свойства или значения.
* Возвращает пустую ссылку, если полезная нагрузка содержит литерал `null` JSON.

<xref:System.Text.Json> хранит упакованный `JsonElement` как для простых, так и для сложных значений при десериализации в <xref:System.Object>, например:

* Свойство `object`.
* Значение словаря `object`.
* Тип массива `object`.
* Корневой `object`.

Однако `System.Text.Json` обрабатывает `null` так же, как `Newtonsoft.Json`, и возвращает пустую ссылку, если полезная нагрузка содержит литерал `null` JSON.

Чтобы реализовать определение типа для свойств `object`, создайте преобразователь, как в примере в разделе [Написание пользовательских преобразователей](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).

### <a name="deserialize-null-to-non-nullable-type"></a>Десериализация значения NULL в тип, не допускающий значения NULL

`Newtonsoft.Json` не создает исключение в следующем сценарии:

* `NullValueHandling` имеет значение `Ignore`.
* Во время десериализации JSON содержит значение NULL для типа значения, не допускающего значения NULL.

В том же сценарии <xref:System.Text.Json> создает исключение. (Соответствующий параметр обработки значений NULL — <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.)

Если вы владеете типом целевого объекта, лучшим обходным решением будет сделать соответствующее свойство допускающим значение NULL (например, изменить `int` на `int?`).

Еще один обходной путь — сделать преобразователь для типа, как в следующем примере, который обрабатывает значения NULL для типов `DateTimeOffset`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetNullHandlingConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь, [используя атрибут для свойства](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

**Примечание.** Предыдущий преобразователь **обрабатывает значения NULL иначе**, чем `Newtonsoft.Json` для POCO, которые указывают значения по умолчанию. Например, следующий код представляет целевой объект:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Предположим, что следующий JSON десериализуется с помощью предыдущего преобразователя:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

После десериализации свойство `Date` имеет значение 1/1/0001 (`default(DateTimeOffset)`), то есть значение, заданное в конструкторе, перезаписывается. При наличии одних и тех же POCO и JSON десериализация `Newtonsoft.Json` оставляет значение 1/1/2001 в свойстве `Date`.

### <a name="deserialize-to-immutable-classes-and-structs"></a>Десериализация в неизменяемые классы и структуры

`Newtonsoft.Json` может выполнять десериализацию в неизменяемые классы и структуры, так как он может использовать конструкторы с параметрами. <xref:System.Text.Json> поддерживает только открытые конструкторы без параметров. В качестве обходного решения можно вызвать конструктор с параметрами в пользовательском преобразователе.

Ниже приведена неизменяемая структура с несколькими параметрами конструктора:

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePoint.cs#ImmutablePoint)]

А вот преобразователь, который сериализует и десериализует эту структуру:

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePointConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь, [добавив его](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Пример подобного преобразователя, обрабатывающего открытые универсальные свойства, см. в разделе [Встроенный преобразователь для пар "ключ-значение"](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).

### <a name="specify-constructor-to-use"></a>Указание конструктора для использования

Атрибут `Newtonsoft.Json` `[JsonConstructor]` позволяет указать, какой конструктор вызывать при десериализации в POCO. <xref:System.Text.Json> поддерживает только конструкторы без параметров. В качестве обходного решения можно вызвать нужный конструктор в пользовательском преобразователе. См. пример [десериализации в неизменяемые классы и структуры](#deserialize-to-immutable-classes-and-structs).

### <a name="required-properties"></a>Обязательные свойства

В `Newtonsoft.Json` вы указываете, что свойство является обязательным, задав `Required` для атрибута `[JsonProperty]`. `Newtonsoft.Json` создает исключение, если в JSON не получено значение для свойства, помеченного как обязательное.

<xref:System.Text.Json> не создает исключение, если для одного из свойств целевого типа не получено значение. Например, у вас есть класс `WeatherForecast`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

Следующий JSON десериализуется без ошибки:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Чтобы десериализация завершалась ошибкой, когда в JSON отсутствуют свойства `Date`, реализуйте пользовательский преобразователь. Следующий пример кода преобразователя создает исключение, если после десериализации свойство `Date` не задано:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь, [добавив его](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.

Для использования этого шаблона рекурсивного вызова преобразователя необходимо зарегистрировать преобразователь с помощью <xref:System.Text.Json.JsonSerializerOptions>, а не с помощью атрибута. При регистрации с помощью атрибута пользовательский преобразователь рекурсивно вызывает сам себя. Результатом является бесконечный цикл, который заканчивается исключением переполнения стека.

При регистрации преобразователя с помощью объекта options следует избегать бесконечного цикла, поэтому не передавайте объект options при рекурсивном вызове <xref:System.Text.Json.JsonSerializer.Serialize%2A> или <xref:System.Text.Json.JsonSerializer.Deserialize%2A>. Объект options содержит коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters%2A>. Если передать его в `Serialize` или `Deserialize`, пользовательский преобразователь вызывает сам себя и делает бесконечный цикл, который приводит к исключению переполнения стека. Если параметры по умолчанию нецелесообразны, создайте новый экземпляр параметров с нужными настройками. Этот подход отнимет много времени, так как каждый новый экземпляр кэшируется независимо.

Существует альтернативный шаблон, который может использовать регистрацию `JsonConverterAttribute` в классе, подлежащем преобразованию. В таком случае код преобразователя вызывает `Serialize` или `Deserialize` для класса, производного от класса, который требуется преобразовать. К производному классу не применен `JsonConverterAttribute`. В следующем примере этого варианта:

* `WeatherForecastWithRequiredPropertyConverterAttribute` — класс, который подлежит десериализации и к которому применен `JsonConverterAttribute`;
* `WeatherForecastWithoutRequiredPropertyConverterAttribute` — производный класс без атрибута преобразователя.
* Код в преобразователе вызывает `Serialize`и `Deserialize` в `WeatherForecastWithoutRequiredPropertyConverterAttribute`, чтобы избежать бесконечного цикла. Этот подход к сериализации приводит к снижению производительности, так как создается дополнительный объект и копируются значения свойств.

Ниже приведены типы `WeatherForecast*`.

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithReqPptyConverterAttr)]

Ниже приведен преобразователь.

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverterForAttributeRegistration.cs)]

Если необходимо обрабатывать атрибуты (например, [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) или различные параметры (например, пользовательские кодировщики)), преобразователю свойств потребуется дополнительная логика. Кроме того, пример кода не обрабатывает свойства, для которых в конструкторе задано значение по умолчанию. И этот подход не различает следующие сценарии:

* В JSON отсутствует свойство.
* Свойство для типа, не допускающего значения NULL, содержится в JSON, но значение является значением по умолчанию для типа, например ноль для `int`.
* Свойство для типа значения, допускающего значение NULL, содержится в JSON, но значение равно NULL.

### <a name="conditionally-ignore-a-property"></a>Условное игнорирование свойства

`Newtonsoft.Json` имеет несколько способов условно игнорировать свойство при сериализации или десериализации:

* `DefaultContractResolver` позволяет выбирать свойства для включения или исключения на основе произвольных критериев.
* Параметры `NullValueHandling` и `DefaultValueHandling` для `JsonSerializerSettings` позволяют указать, что все свойства со значением NULL или значениями по умолчанию должны игнорироваться.
* Параметры `NullValueHandling` и `DefaultValueHandling` атрибута `[JsonProperty]` позволяют указать отдельные свойства, которые должны игнорироваться при установке значения NULL или значения по умолчанию.

<xref:System.Text.Json> предоставляет следующие способы опустить свойства при сериализации:

* Атрибут [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) в свойстве приводит к исключению свойства из JSON во время сериализации.
* Глобальный параметр [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) позволяет исключить все свойства со значением NULL.
* Глобальный параметр [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) позволяет исключить все свойства только для чтения.

Эти параметры **не** позволяют:

* Игнорировать все свойства, имеющие значение по умолчанию для типа.
* Игнорировать выбранные свойства, имеющие значение по умолчанию для типа.
* Игнорировать выбранные свойства, если их значение равно NULL.
* Игнорировать выбранные свойства на основе произвольных критериев, вычисляемых во время выполнения.

Для этой функции можно написать пользовательский преобразователь. Ниже приведен пример POCO и пользовательского преобразователя, демонстрирующий этот подход:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

Преобразователь вызывает исключение свойства `Summary` из сериализации, если его значение — NULL, пустая строка или "N/A".

Зарегистрируйте этот пользовательский преобразователь, [используя атрибут для класса](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) или [добавив преобразователь](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Этот подход требует дополнительной логики, если:

* POCO включает сложные свойства.
* Необходимо выполнять обработку таких атрибутов, как `[JsonIgnore]`, или таких параметров, как пользовательские кодировщики.

### <a name="specify-date-format"></a>Указание формата даты

`Newtonsoft.Json` предоставляет несколько способов управления сериализацией и десериализации свойств `DateTime` и типов `DateTimeOffset`:

* Параметр `DateTimeZoneHandling` можно использовать для сериализации всех значений `DateTime` как даты в формате UTC.
* Параметры `DateFormatString` и преобразователи `DateTime` можно использовать для настройки формата строк даты.

В <xref:System.Text.Json> единственным форматом со встроенной поддержкой является ISO 8601-1:2019, так как он широко используется, выражен однозначно и обеспечивает точные круговые пути. Чтобы использовать любой другой формат, создайте пользовательский преобразователь. Дополнительные сведения см. в разделе [Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md).

### <a name="callbacks"></a>Обратные вызовы

`Newtonsoft.Json` позволяет выполнять пользовательский код в нескольких точках процесса сериализации или десериализации:

* OnDeserializing (в начале десериализации объекта)
* OnDeserialized (после десериализации объекта)
* OnSerializing (в начале сериализации объекта)
* OnSerialized (после сериализации объекта)

В <xref:System.Text.Json> можно имитировать обратные вызовы, написав пользовательский преобразователь. В следующем примере показан пользовательский преобразователь для POCO. Этот преобразователь включает код, отображающий сообщение в каждой точке, которая соответствует обратному вызову `Newtonsoft.Json`.

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastCallbacksConverter.cs)]

Зарегистрируйте этот пользовательский преобразователь, [добавив его](system-text-json-converters-how-to.md#registration-sample---converters-collection) в коллекцию <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Если вы используете пользовательский преобразователь, как в предыдущем примере:

* Код `OnDeserializing` не имеет доступа к новому экземпляру POCO. Чтобы управлять новым экземпляром POCO в начале десериализации, вставьте этот код в конструктор POCO.
* Избегайте бесконечного цикла, регистрируя преобразователь с помощью объекта options и не передавая объект options при рекурсивном вызове `Serialize` или `Deserialize`.

Дополнительные сведения о пользовательских преобразователях, которые рекурсивно вызывают `Serialize` или `Deserialize`, см. в разделе [Обязательные свойства](#required-properties) ранее в этой статье.

### <a name="public-and-non-public-fields"></a>Открытые и не открытые поля

`Newtonsoft.Json` может выполнять сериализацию и десериализацию полей, а также свойств. <xref:System.Text.Json> работает только с общими свойствами. Эта функция может быть предоставлена пользовательскими преобразователями.

### <a name="internal-and-private-property-setters-and-getters"></a>Методы задания и получения для внутренних и закрытых свойств

`Newtonsoft.Json` может использовать методы задания и получения частных и внутренних свойств с помощью атрибута `JsonProperty`. <xref:System.Text.Json> поддерживает только открытые методы задания. Эта функция может быть предоставлена пользовательскими преобразователями.

### <a name="populate-existing-objects"></a>Заполнение существующих объектов

Метод `JsonConvert.PopulateObject` в `Newtonsoft.Json` десериализует документ JSON в существующий экземпляр класса вместо создания нового экземпляра. <xref:System.Text.Json> всегда создает новый экземпляр целевого типа с помощью открытого конструктора без параметров по умолчанию. Пользовательские преобразователи можно десериализовать в существующий экземпляр.

### <a name="reuse-rather-than-replace-properties"></a>Повторное использование вместо замены свойств

Параметр `Newtonsoft.Json` `ObjectCreationHandling` позволяет указать, что объекты в свойствах следует использовать повторно, а не заменять во время десериализации. <xref:System.Text.Json> всегда заменяет объекты в свойствах.  Эта функция может быть предоставлена пользовательскими преобразователями.

### <a name="add-to-collections-without-setters"></a>Добавление в коллекции без методов задания

Во время десериализации `Newtonsoft.Json` добавляет объекты в коллекцию, даже если свойство не имеет метода задания. <xref:System.Text.Json> игнорирует свойства, у которых нет методов задания. Эта функция может быть предоставлена пользовательскими преобразователями.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Сценарии, которые JsonSerializer в настоящее время не поддерживает

В следующих сценариях обходные пути являются нецелесообразными или невозможными. Если вы используете эти функции `Newtonsoft.Json`, миграция будет невозможна без существенных изменений.

### <a name="preserve-object-references-and-handle-loops"></a>Сохранение ссылок на объекты и обработка циклов

По умолчанию `Newtonsoft.Json` сериализуется по значению. Например, если объект включает два свойства, которые содержат ссылку на один и тот же объект `Person`, значения свойств этого объекта `Person` дублируются в JSON.

У `Newtonsoft.Json` параметр `PreserveReferencesHandling` имеет значение `JsonSerializerSettings`, что позволяет выполнять сериализацию по ссылке:

* Метаданные идентификатора добавляются в JSON, созданный для первого объекта `Person`.
* JSON, созданный для второго объекта `Person`, содержит ссылку на этот идентификатор вместо значений свойств.

`Newtonsoft.Json` также имеет параметр `ReferenceLoopHandling`, который позволяет игнорировать циклические ссылки, а не создавать исключение.

<xref:System.Text.Json> поддерживает только сериализацию по значению и создает исключение для циклических ссылок.

### <a name="systemruntimeserialization-attributes"></a>Атрибуты System.Runtime.Serialization

<xref:System.Text.Json> не поддерживает атрибуты из пространства имен `System.Runtime.Serialization`, такие как `DataMemberAttribute` и `IgnoreDataMemberAttribute`.

### <a name="octal-numbers"></a>Числа восьмеричной системы

`Newtonsoft.Json` обрабатывает числа с начальным нулем как восьмеричные числа. <xref:System.Text.Json> не допускает начальные нули, так как спецификация [RFC 8259](https://tools.ietf.org/html/rfc8259) не разрешает их.

### <a name="missingmemberhandling"></a>MissingMemberHandling

`Newtonsoft.Json` можно настроить для создания исключений во время десериализации, если в JSON включены свойства, отсутствующие в целевом типе. <xref:System.Text.Json> игнорирует дополнительные свойства в JSON, за исключением случаев, когда используется атрибут [[JsonExtensionData]](system-text-json-how-to.md#handle-overflow-json). Для функции отсутствующих членов не существует обходного решения.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json` позволяет выполнять отладку с помощью `TraceWriter` для просмотра журналов, созданных при сериализации или десериализации. <xref:System.Text.Json> не ведет журнал.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JsonDocument и JsonElement в сравнении с JToken (например, JObject, JArray)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> предоставляет возможность выполнять синтаксический анализ и сборку модели DOM **только для чтения** из существующих полезных данных JSON. Модель DOM предоставляет произвольный доступ к данным в полезных данных JSON. Доступ к элементам JSON, составляющим полезные данные, можно получить с помощью типа <xref:System.Text.Json.JsonElement>. Тип `JsonElement` предоставляет интерфейсы API для преобразования текста JSON в общие типы .NET. `JsonDocument` предоставляет свойство <xref:System.Text.Json.JsonDocument.RootElement>.

### <a name="jsondocument-is-idisposable"></a>JsonDocument является IDisposable

`JsonDocument` создает выполняющееся в памяти представление данных в едином буфере. Таким образом, в отличие от `JObject` или `JArray` из `Newtonsoft.Json`, тип `JsonDocument` реализует `IDisposable` и должен использоваться внутри блока using.

Возвращайте `JsonDocument` из API только в том случае, если хотите передать владение временем существования и ответственность вызывающему объекту. В большинстве случаев это необязательно. Если вызывающему объекту необходимо работать со всем документом JSON, возвращайте <xref:System.Text.Json.JsonElement.Clone%2A> <xref:System.Text.Json.JsonDocument.RootElement%2A>, то есть <xref:System.Text.Json.JsonElement>. Если вызывающему объекту необходимо работать с определенным элементом в документе JSON, возвращайте <xref:System.Text.Json.JsonElement.Clone%2A> этого <xref:System.Text.Json.JsonElement>. Если вы возвращаете `RootElement` или вложенный элемент напрямую, не выполняя `Clone`, вызывающий объект не сможет получить доступ к возвращаемому объекту `JsonElement` после того, как `JsonDocument`, которому он принадлежит, будет удален.

Ниже приведен пример, в котором необходимо сделать `Clone`.

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

Приведенный выше код ждет `JsonElement`, содержащий свойство `fileName`. Он открывает JSON-файл и создает `JsonDocument`. Метод предполагает, что вызывающий объект хочет работать со всем документом, поэтому он возвращает `Clone` `RootElement`.

Если вы получаете `JsonElement` и возвращаете вложенный элемент, нет необходимости возвращать `Clone` вложенного элемента. Вызывающий объект отвечает за поддержание активности `JsonDocument`, которому принадлежит переданный `JsonElement`. Пример:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument доступен только для чтения

Модель DOM <xref:System.Text.Json> не может добавлять, удалять или изменять элементы JSON. Она разработана таким образом для повышения производительности и сокращения количества распределений для анализа полезных данных JSON обычного размера (то есть < 1 МБ). Если в вашем сценарии используется изменяемая модель DOM, возможны следующие обходные пути.

* Чтобы создать `JsonDocument` с нуля (то есть без передачи существующих полезных данных JSON в метод `Parse`), напишите текст JSON с помощью `Utf8JsonWriter` и проанализируйте выходные данные, чтобы создать новый `JsonDocument`.
* Чтобы изменить существующий `JsonDocument`, используйте его для написания текста JSON, внося изменения во время написания, и проанализируйте выходные данные для создания нового `JsonDocument`.
* Сведения о слиянии существующих документов JSON, эквивалентных API `JObject.Merge` или `JContainer.Merge` из `Newtonsoft.Json`, см. в [этой проблеме GitHub](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).

### <a name="jsonelement-is-a-union-struct"></a>JsonElement является структурой объединения

`JsonDocument` предоставляет `RootElement` как свойство типа <xref:System.Text.Json.JsonElement>, которое представляет собой объединение, тип структуры, охватывающий любой элемент JSON. `Newtonsoft.Json` использует выделенные иерархические типы, такие как `JObject`, `JArray`, `JToken` и т. д. `JsonElement` можно использовать для поиска и перечисления, а с помощью `JsonElement` можно материализовывать элементы JSON в типы .NET.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>Поиск вложенных элементов в JsonDocument и JsonElement

Поиск токенов JSON с помощью `JObject` или `JArray` из `Newtonsoft.Json`, как правило, выполняется относительно быстро, так как они присутствуют в словаре. Зато поиск по `JsonElement` требует последовательного поиска свойств и, следовательно, занимает относительно много времени (например, при использовании `TryGetProperty`). <xref:System.Text.Json> предназначен для сокращения времени начального анализа, а не времени поиска. Поэтому рекомендуется использовать следующие подходы для оптимизации производительности при поиске по объекту `JsonDocument`:

* Используйте встроенные перечислители (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> и <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) вместо создания собственных индексов или циклов.
* Не выполняйте последовательный поиск по всему `JsonDocument` в каждом свойстве с помощью `RootElement`. Вместо этого выполните поиск по вложенным объектам JSON на основе известной структуры данных JSON. Например, если вы ищете свойство `Grade` в объектах `Student`, пройдите по объектам `Student` и получите значение `Grade` для каждого из них, вместо того, чтобы проходить по всем объектам `JsonElement` в поисках свойств `Grade`. Последний метод приведет к ненужным проходам по тем же данным.

Пример кода см. в разделе [Использование JsonDocument для доступа к данным](system-text-json-how-to.md#use-jsondocument-for-access-to-data).

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Сравнение Utf8JsonReader и JsonTextReader

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> — это последовательный модуль чтения текста JSON в кодировке UTF-8 с высокой производительностью и низким уровнем распределения, при этом чтение выполняется из [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) или [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601). `Utf8JsonReader` — это низкоуровневый тип, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы.

В следующих разделах описываются рекомендуемые шаблоны программирования для использования `Utf8JsonReader`.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader является структурой ссылок

Поскольку тип `Utf8JsonReader` является *структурой ссылок*, он имеет [определенные ограничения](../../csharp/language-reference/builtin-types/struct.md#ref-struct). Например, он не может храниться как поле в классе или структуре, отличной от структуры ссылки. Для достижения высокой производительности этот тип должен быть `ref struct`, поскольку ему необходимо кэшировать входной объект [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), который сам по себе является структурой ссылок. Кроме того, этот тип является изменяемым, так как имеет состояние. Поэтому **передавайте его по ссылке**, а не по значению. Передача его по значению приведет к копированию структуры, и изменения состояния не будут видны вызывающему объекту. Это отличается от `Newtonsoft.Json`, так как `Newtonsoft.Json` `JsonTextReader` является классом. Дополнительные сведения об использовании структур ссылок см. в статье [Написание безопасного и эффективного кода C#](../../csharp/write-safe-efficient-code.md).

### <a name="read-utf-8-text"></a>Чтение текста UTF-8

Для достижения наилучшей производительности при использовании `Utf8JsonReader` читайте полезные данные JSON, уже закодированные как текст UTF-8, а не как строки UTF-16. Пример кода см. в разделе [Фильтрация данных с помощью Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).

### <a name="read-with-a-stream-or-pipereader"></a>Чтение с помощью Stream или PipeReader

`Utf8JsonReader` поддерживает чтение [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) или [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) в кодировке UTF-8 (результат чтения из <xref:System.IO.Pipelines.PipeReader>).

Для синхронного чтения можно считывать полезные данные JSON до конца потока в массив байтов и передать его в модуль чтения. Для чтения из строки (в кодировке UTF-16) вызовите <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A>, чтобы сначала перекодировать строку в массив байтов в кодировке UTF-8. Затем передайте данные в `Utf8JsonReader`.

Поскольку `Utf8JsonReader` считает входные данные текстом JSON, метка порядка байтов UTF-8 считается недопустимым JSON. Вызывающий объект должен использовать фильтр, прежде чем передавать данные в модуль чтения.

Примеры кода см. в разделе [Использование Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).

### <a name="read-with-multi-segment-readonlysequence"></a>Чтение с помощью ReadOnlySequence с несколькими сегментами

Если входные данные JSON являются [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), к каждому элементу JSON можно получить доступ из свойства `ValueSpan` в модуле чтения при проходе цикла чтения. Однако если входными данными является [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (результат чтения из <xref:System.IO.Pipelines.PipeReader>), некоторые элементы JSON могут создать несколько сегментов объекта `ReadOnlySequence<byte>`. Эти элементы не будут доступны из <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> в непрерывном блоке памяти. Вместо этого каждый раз, когда у вас есть `ReadOnlySequence<byte>` с несколькими сегментами в качестве входных данных, следует опросить свойство <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> в модуле чтения, чтобы выяснить, как получить доступ к текущему элементу JSON. Вот рекомендуемый шаблон:

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a>Использование ValueTextEquals для поиска имени свойства

Не используйте <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> для побайтового сравнения путем вызова <xref:System.MemoryExtensions.SequenceEqual%2A> для поиска имени свойства. Вместо этого вызовите <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>, так как этот метод отменяет экранирование всех символов, которые экранированы в JSON. Ниже приведен пример, демонстрирующий поиск свойства с именем name:

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>Считывание значений NULL в типы значений, допускающие значения NULL

`Newtonsoft.Json` предоставляет API, которые возвращают <xref:System.Nullable%601>, например `ReadAsBoolean`, который обрабатывает `Null` `TokenType`, возвращая `bool?`. Встроенные API `System.Text.Json` возвращают только типы значений, не допускающие значения NULL. Например, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> возвращает `bool`. Он вызывает исключение, если обнаруживает `Null` в JSON. В следующих примерах показаны два способа обработки значений NULL: возврат типа значения, допускающего значение NULL, и возврат значения по умолчанию:

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a>Настройка для различных версий

Если необходимо продолжить использование `Newtonsoft.Json` для определенных целевых платформ, можно выбрать несколько версий и создать две реализации. Однако это нестандартный подход, и потребуется несколько `#ifdefs` и дублирование источника. Одним из способов совместного использования максимально возможного объема кода является создание оболочки `ref struct` вокруг `Utf8JsonReader` и `Newtonsoft.Json` `JsonTextReader`. Эта оболочка будет объединять общедоступную контактную зону при изоляции различий в поведении. Это позволяет изолировать изменения, сведя их, в основном, к созданию типа, а также передаче нового типа по ссылке. Это шаблон, которому следует библиотека [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/):

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Сравнение Utf8JsonWriter и JsonTextWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> — это высокопроизводительный способ записать текст JSON в кодировке UTF-8 из распространенных типов .NET, например `String`, `Int32` и `DateTime`. Модуль записи — это низкоуровневый тип, с помощью которого можно создавать пользовательские сериализаторы.

В следующих разделах описываются рекомендуемые шаблоны программирования для использования `Utf8JsonWriter`.

### <a name="write-with-utf-8-text"></a>Запись с помощью текста UTF-8

Для достижения наилучшей производительности при использовании `Utf8JsonWriter` записывайте полезные данные JSON, уже закодированные как текст UTF-8, а не как строки UTF-16. Используйте <xref:System.Text.Json.JsonEncodedText>, чтобы кэшировать и предварительно закодировать известные имена и значения свойств строки как статические, а затем передать их в модуль записи вместо использования строковых литералов UTF-16. Это быстрее, чем кэширование и использование байтовых массивов UTF-8.

Этот подход также работает, если необходимо выполнить пользовательское экранирование. `System.Text.Json` не позволяет отключить экранирование при записи строки. Однако можно передать собственный пользовательский <xref:System.Text.Encodings.Web.JavaScriptEncoder> в качестве параметра для модуля записи или создать собственный `JsonEncodedText`, который использует `JavascriptEncoder` для выполнения экранирования, а затем написать `JsonEncodedText` вместо строки. Дополнительные сведения см. в статье [Настройка кодировки символов](system-text-json-how-to.md#customize-character-encoding).

### <a name="write-raw-values"></a>Запись необработанных значений

Метод `Newtonsoft.Json` `WriteRawValue` записывает необработанный код JSON, где ожидается значение. <xref:System.Text.Json> не имеет прямого эквивалента, но ниже приведено обходное решение, обеспечивающее запись только допустимого JSON:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Настройка экранирования символов

Параметр [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) `JsonTextWriter` предлагает варианты для экранирования всех символов, не являющихся символами ASCII, **или** символов HTML. По умолчанию `Utf8JsonWriter` экранирует все символы, отличные от ASCII, **и** символы HTML. Такое экранирование выполняется в целях глубокой защиты. Чтобы указать другую политику экранирования, создайте <xref:System.Text.Encodings.Web.JavaScriptEncoder> и задайте <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>. Дополнительные сведения см. в статье [Настройка кодировки символов](system-text-json-how-to.md#customize-character-encoding).

### <a name="customize-json-format"></a>Настройка формата JSON

`JsonTextWriter` включает следующие параметры, для которых `Utf8JsonWriter` не имеет эквивалента:

* [Отступ](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) — задает количество символов для отступа. `Utf8JsonWriter` всегда имеет 2-символьный отступ.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) — указывает символ, используемый для отступа.  `Utf8JsonWriter` всегда использует пробелы.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) — указывает символ, используемый для заключения строковых значений.  `Utf8JsonWriter` всегда использует двойные кавычки.
* [QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) — указывает, следует ли заключать имена свойств в кавычки.  `Utf8JsonWriter` всегда заключает их в кавычки.

Не существует обходных решений, которые позволяют настроить JSON, созданный `Utf8JsonWriter` такими методами.

### <a name="write-null-values"></a>Запись значений NULL

Чтобы записать значения NULL с помощью `Utf8JsonWriter`, вызовите:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> для записи пары "ключ-значение" со значением NULL.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> для записи значения NULL в качестве элемента массива JSON.

Для строкового свойства, если строка имеет значение NULL, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> и <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> эквивалентны `WriteNull` и `WriteNullValue`.

### <a name="write-timespan-uri-or-char-values"></a>Запись значений TimeSpan, URI или char

`JsonTextWriter` предоставляет методы `WriteValue` для значений [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [URI](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm) и [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm). `Utf8JsonWriter` не имеет эквивалентных методов. Вместо этого следует отформатировать эти значения как строки (например, вызвав `ToString()`) и вызвать <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.

### <a name="multi-targeting"></a>Настройка для различных версий

Если необходимо продолжить использование `Newtonsoft.Json` для определенных целевых платформ, можно выбрать несколько версий и создать две реализации. Однако это нестандартный подход, и потребуется несколько `#ifdefs` и дублирование источника. Одним из способов совместного использования максимально возможного объема кода является создание оболочки вокруг `Utf8JsonWriter` и `Newtonsoft` `JsonTextWriter`. Эта оболочка будет объединять общедоступную контактную зону при изоляции различий в поведении. Это позволяет изолировать изменения и свести их, в основном, к созданию типа. Библиотека [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) следует:

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Дополнительные ресурсы

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Как использовать System.Text.Json](system-text-json-how-to.md)
* [Практическое руководство. Написание настраиваемых преобразователей](system-text-json-converters-how-to.md)
* [Поддержка DateTime и DateTimeOffset в System.Text.Json](../datetime/system-text-json-support.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
* [Справочник по API System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
