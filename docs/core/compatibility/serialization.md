---
title: Критические изменения в категории сериализации
description: Перечень критических изменений в категории сериализации в .NET Core и .NET 5.0 и более поздних версий.
ms.date: 07/30/2020
ms.openlocfilehash: 65006e6fb45ed2d54699c9972e0489e3ac5ac8bc
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955344"
---
# <a name="serialization-breaking-changes"></a>Критические изменения в категории сериализации

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленные версии |
| - | - |
| [JsonSerializer.Serialize вызывает исключение ArgumentNullException, если параметр типа имеет значение null](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | 5.0 |
| [Для JsonSerializer.Deserialize требуется строка из одного символа](#jsonserializerdeserialize-requires-single-character-string) | 5.0 |
| [Метод BinaryFormatter.Deserialize повторно изолирует некоторые исключения в классе SerializationException](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
