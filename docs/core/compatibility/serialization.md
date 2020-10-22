---
title: Критические изменения в категории сериализации
description: Перечень критических изменений в категории сериализации в .NET Core и .NET 5.0 и более поздних версий.
ms.date: 07/30/2020
ms.openlocfilehash: bb6bd650afeba426edc6e102076f05f97f8e0598
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050480"
---
# <a name="serialization-breaking-changes"></a>Критические изменения в категории сериализации

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленные версии |
| - | - |
| [Параметры PropertyNamingPolicy, PropertyNameCaseInsensitive и Encoder учитываются при сериализации и десериализации пар "ключ-значение"](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | 5.0 |
| [Не являющиеся открытыми конструкторы без параметров не используются для десериализации](#non-public-parameterless-constructors-not-used-for-deserialization) | 5.0 |
| [JsonSerializer.Serialize вызывает исключение ArgumentNullException, если параметр типа имеет значение null](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | 5.0 |
| [Для JsonSerializer.Deserialize требуется строка из одного символа](#jsonserializerdeserialize-requires-single-character-string) | 5.0 |
| [Метод BinaryFormatter.Deserialize повторно изолирует некоторые исключения в классе SerializationException](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

***

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

***

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
