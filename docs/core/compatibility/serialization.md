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
# <a name="serialization-breaking-changes"></a><span data-ttu-id="8fce3-103">Критические изменения в категории сериализации</span><span class="sxs-lookup"><span data-stu-id="8fce3-103">Serialization breaking changes</span></span>

<span data-ttu-id="8fce3-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="8fce3-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="8fce3-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="8fce3-105">Breaking change</span></span> | <span data-ttu-id="8fce3-106">Представленные версии</span><span class="sxs-lookup"><span data-stu-id="8fce3-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="8fce3-107">JsonSerializer.Serialize вызывает исключение ArgumentNullException, если параметр типа имеет значение null</span><span class="sxs-lookup"><span data-stu-id="8fce3-107">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="8fce3-108">5.0</span><span class="sxs-lookup"><span data-stu-id="8fce3-108">5.0</span></span> |
| [<span data-ttu-id="8fce3-109">Для JsonSerializer.Deserialize требуется строка из одного символа</span><span class="sxs-lookup"><span data-stu-id="8fce3-109">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="8fce3-110">5.0</span><span class="sxs-lookup"><span data-stu-id="8fce3-110">5.0</span></span> |
| [<span data-ttu-id="8fce3-111">Метод BinaryFormatter.Deserialize повторно изолирует некоторые исключения в классе SerializationException</span><span class="sxs-lookup"><span data-stu-id="8fce3-111">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="8fce3-112">5.0</span><span class="sxs-lookup"><span data-stu-id="8fce3-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="8fce3-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="8fce3-113">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
