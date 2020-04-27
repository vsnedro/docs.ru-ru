---
ms.openlocfilehash: 2afe5ae80c2d7feca89737b767a6335950d04416
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021639"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a>Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder

Начиная с .NET Core 3.0 (предварительная версия 8) методы <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> содержат необязательный аргумент <xref:System.Text.Encodings.Web.JavaScriptEncoder>.

#### <a name="change-description"></a>Описание изменений

.NET Core 3.0 включает новый тип xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>. Начиная с .NET Core 3 0 (предварительная версия 8) сигнатура всех перегрузок метода <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> включает необязательный параметр <xref:System.Text.Encodings.Web.JavaScriptEncoder>. Это изменение позволяет использовать другой или пользовательский кодировщик.

Сигнатура методов `Encode` в NET Core 3.0 (предварительная версия 7):

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value);
        public static JsonEncodedText Encode(string value);
    }
}
```

Сигнатура тех же методов `Encode` в NET Core 3.0 (предварительная версия 8 и последующие версии):

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(string value, JavaScriptEncoder encoder = null);
    }
}
```

#### <a name="version-introduced"></a>Представленная версия

.NET Core 3.0 (предварительная версия 8)

#### <a name="recommended-action"></a>Рекомендованное действие

Это критическое изменение касается только двоичного кода. При повторной компиляции для .NET Core 3.0 (предварительная версия 8 и последующие версии) все проблемы среды выполнения будут исправлены.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
