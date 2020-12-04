---
title: Критическое изменение. Для десериализации требуется строка из одного символа
description: Сведения о критическом изменении в .NET 5.0, где для JsonSerializer.Deserialize требуется строка из одного символа.
ms.date: 10/18/2020
ms.openlocfilehash: 780f2928d776ecb6db9a7fc05a720e889eb363e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759970"
---
# <a name="jsonserializerdeserialize-requires-single-character-string"></a>Для JsonSerializer.Deserialize требуется строка из одного символа

Если параметр типа имеет значение <xref:System.Char>, строковый аргумент для <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> должен содержать один символ для выполнения десериализации.

## <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET, если строка с несколькими символами передается в <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> и параметр типа равен <xref:System.Char>, десериализация выполняется успешно, но десериализуется только первый символ.

В .NET 5.0 и более поздних версиях, когда параметр типа равен <xref:System.Char>, передача любой, кроме односимвольной, строки приводит к вызову исключения <xref:System.Text.Json.JsonException>.

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="reason-for-change"></a>Причина изменения

<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> выполняет синтаксический анализ текста, представляющего одно значение JSON, в экземпляр типа, заданного параметром универсального типа. Синтаксический анализ должен выполняться только тогда, когда предоставленные полезные данные допустимы для указанного параметра универсального типа. Для типа значения <xref:System.Char> допустимые полезные данные представляют собой строку из одного символа.

## <a name="recommended-action"></a>Рекомендованное действие

При синтаксическом анализе строки в тип <xref:System.Char> с помощью <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>убедитесь, что строка состоит из одного символа.

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
