---
title: Критическое изменение. Для десериализации символа требуется строка из одного символа
description: Сведения о критическом изменении в .NET 5.0, где System.Text.Json требует наличия в JSON строки с одним символом при десериализации до целевого символа.
ms.date: 12/15/2020
ms.openlocfilehash: 39a2d25b00bf8855cfbf46a4d78b8545052703e5
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633875"
---
# <a name="systemtextjson-requires-single-char-string-to-deserialize-a-char"></a>Для десериализации символа в System.Text.Json требуется строка из одного символа

Для успешной десериализации <xref:System.Char> с помощью <xref:System.Text.Json>строка JSON должна содержать один символ.

## <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET строка из нескольких `char` в JSON успешно десериализуется в свойство `char` или поле. Используется только первый `char` строки, как показано в следующем примере:

```csharp
// .NET Core 3.0 and 3.1: Returns the first char 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one char.
char deserializedChar = JsonSerializer.Deserialize<char>("\"abc\"");
```

В .NET 5.0 и более поздних версиях передача любой строки, кроме строки с одним `char`, приводит к вызову исключения <xref:System.Text.Json.JsonException>, если целевым объектом десериализации является `char`. Следующий пример строки успешно десериализуется во всех версиях .NET:

```csharp
// Correct usage.
char deserializedChar = JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="reason-for-change"></a>Причина изменения

Синтаксический анализ для сериализации должен выполняться только тогда, когда предоставленные полезные данные допустимы для целевого типа. Для типа `char` единственным допустимым набором полезных данных является строка с одним `char`.

## <a name="recommended-action"></a>Рекомендованное действие

При десериализации JSON в целевой объект `char` убедитесь, что строка состоит из одного `char`.

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`

### Category

Serialization

-->
