---
title: Критическое изменение. При сериализации создается исключение, если параметр типа имеет значение NULL
description: Сведения о критическом изменении в .NET 5.0, где методы сериализации JsonSerializer.Serialize с параметром Type теперь вызывают исключение, если этот параметр имеет значение NULL
ms.date: 10/18/2020
ms.openlocfilehash: af2885394418072ad7efec5855490b5b80152fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759946"
---
# <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a>JsonSerializer.Serialize вызывает исключение ArgumentNullException, если параметр типа имеет значение null

Перегрузки <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType> и <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> с параметром типа <xref:System.Type> теперь вызывают исключение <xref:System.ArgumentNullException>, когда для параметра передается значение `null`.

## <a name="change-description"></a>Описание изменений

В .NET Core 3.1 перегрузки <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> и <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>, имеющие параметр <xref:System.Type>, вызывают исключение <xref:System.ArgumentNullException> при передаче для параметра `Type inputType` значение `null`, но не в том случае, если параметр `Object value` также равен `null`. Начиная с .NET 5.0 эти методы *всегда* вызывают исключение <xref:System.ArgumentNullException> при передаче для параметра <xref:System.Type> значения `null`.

Поведение в .NET Core 3.1:

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

Поведение в .NET 5.0 и более поздних версиях:

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="reason-for-change"></a>Причина изменения

Передача для параметра `Type inputType` значения `null` неприемлемо и всегда должно вызывать исключение <xref:System.ArgumentNullException>.

## <a name="recommended-action"></a>Рекомендованное действие

Убедитесь, что вы не передаете для параметра `Type inputType` этих методов значение `null`.

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
