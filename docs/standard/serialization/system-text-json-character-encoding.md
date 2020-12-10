---
title: Как настроить кодировку символов с помощью System.Text.Json
description: Узнайте, как в .NET настроить кодировку символов при сериализации в JSON и десериализации из JSON.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: f6a50a3ca2a5e871294cf7c056cbf197a61cd668
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439862"
---
# <a name="how-to-customize-character-encoding-with-no-locsystemtextjson"></a>Как настроить кодировку символов с помощью System.Text.Json

По умолчанию сериализатор экранирует символы, отличные от ASCII. То есть он заменяет их на `\uxxxx`, где `xxxx` является кодом в кодировке Юникода символа. Например, если свойству `Summary` в следующем коде JSON присвоено кириллическое значение `жарко`, то объект `WeatherForecast` сериализуется, как показано в этом примере:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

## <a name="serialize-language-character-sets"></a>Сериализация кодировки языка

Чтобы сериализовать кодировки одного или нескольких языков без экранирования, укажите [диапазон символов Юникода](xref:System.Text.Unicode.UnicodeRanges) при создании экземпляра <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, как показано в следующем примере:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="LanguageSets":::

Этот код не поддерживает символы кириллицы или греческого языка. Если свойству `Summary` присвоено кириллическое значение `жарко`, то объект `WeatherForecast` сериализуется, как показано в этом примере:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Чтобы сериализовать все кодировки языка без экранирования, используйте <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.

## <a name="serialize-specific-characters"></a>Сериализация определенных символов

В качестве альтернативного способа вы можете указать отдельные символы, которые нужно разрешить, без экранирования. В следующем примере сериализуются только первые два символа слова `жарко`:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="SelectedCharacters":::

Ниже приведен пример JSON, созданный с помощью приведенного выше кода.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

## <a name="serialize-all-characters"></a>Сериализация всех символов

Чтобы минимизировать экранирование, можно использовать <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, как показано в следующем примере:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="UnsafeRelaxed":::

> [!CAUTION]
> По сравнению с кодировщиком по умолчанию, кодировщик `UnsafeRelaxedJsonEscaping` более предпочтителен в отношении передачи символов без экранирования:
>
> * Он не выполняет экранирование символов, учитывающих HTML, например `<`, `>`, `&` и `'`.
> * Он не предоставляет никаких дополнительных средств защиты от атак с помощью XSS или раскрытия информации, которые, например, могут возникать из-за того, что клиент и сервер не согласны с *кодировкой*.
>
> Используйте ненадежный кодировщик, только если известно, что клиент будет интерпретировать полученные полезные данные как JSON в кодировке UTF-8. Например, его можно использовать, если сервер отправляет заголовок ответа `Content-Type: application/json; charset=utf-8`. Никогда не допускайте, чтобы необработанные выходные данные `UnsafeRelaxedJsonEscaping` выводились на HTML-страницу или в элемент `<script>`.

## <a name="see-also"></a>См. также раздел

* [Общие сведения о System.Text.Json](system-text-json-overview.md)
* [Написание пользовательских сериализаторов и десериализаторов](write-custom-serializer-deserializer.md)
* [Как написать настраиваемые преобразователи для сериализации JSON (маршалинг) в .NET](system-text-json-converters-how-to.md)
* [Справочник по API System.Text.Json](xref:System.Text.Json)
