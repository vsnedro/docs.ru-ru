---
title: Критические изменения в категории сериализации
description: Перечень критических изменений в категории сериализации в .NET Core и .NET 5.0 и более поздних версий.
ms.date: 07/30/2020
ms.openlocfilehash: 67608c8e7a9745c060b7eb179fe5a956ede9f80f
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332888"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="0ff7c-103">Критические изменения в категории сериализации</span><span class="sxs-lookup"><span data-stu-id="0ff7c-103">Serialization breaking changes</span></span>

<span data-ttu-id="0ff7c-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="0ff7c-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="0ff7c-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="0ff7c-105">Breaking change</span></span> | <span data-ttu-id="0ff7c-106">Представленные версии</span><span class="sxs-lookup"><span data-stu-id="0ff7c-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="0ff7c-107">Приложения ASP.NET Core поддерживают десериализацию заключенных в кавычки чисел</span><span class="sxs-lookup"><span data-stu-id="0ff7c-107">ASP.NET Core apps allow deserializing quoted numbers</span></span>](#aspnet-core-apps-allow-deserializing-quoted-numbers) | <span data-ttu-id="0ff7c-108">5.0</span><span class="sxs-lookup"><span data-stu-id="0ff7c-108">5.0</span></span> |
| [<span data-ttu-id="0ff7c-109">Параметры PropertyNamingPolicy, PropertyNameCaseInsensitive и Encoder учитываются при сериализации и десериализации пар "ключ-значение"</span><span class="sxs-lookup"><span data-stu-id="0ff7c-109">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | <span data-ttu-id="0ff7c-110">5.0</span><span class="sxs-lookup"><span data-stu-id="0ff7c-110">5.0</span></span> |
| [<span data-ttu-id="0ff7c-111">Не являющиеся открытыми конструкторы без параметров не используются для десериализации</span><span class="sxs-lookup"><span data-stu-id="0ff7c-111">Non-public, parameterless constructors not used for deserialization</span></span>](#non-public-parameterless-constructors-not-used-for-deserialization) | <span data-ttu-id="0ff7c-112">5.0</span><span class="sxs-lookup"><span data-stu-id="0ff7c-112">5.0</span></span> |
| [<span data-ttu-id="0ff7c-113">JsonSerializer.Serialize вызывает исключение ArgumentNullException, если параметр типа имеет значение null</span><span class="sxs-lookup"><span data-stu-id="0ff7c-113">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="0ff7c-114">5.0</span><span class="sxs-lookup"><span data-stu-id="0ff7c-114">5.0</span></span> |
| [<span data-ttu-id="0ff7c-115">Для JsonSerializer.Deserialize требуется строка из одного символа</span><span class="sxs-lookup"><span data-stu-id="0ff7c-115">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="0ff7c-116">5.0</span><span class="sxs-lookup"><span data-stu-id="0ff7c-116">5.0</span></span> |
| [<span data-ttu-id="0ff7c-117">Метод BinaryFormatter.Deserialize повторно изолирует некоторые исключения в классе SerializationException</span><span class="sxs-lookup"><span data-stu-id="0ff7c-117">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="0ff7c-118">5.0</span><span class="sxs-lookup"><span data-stu-id="0ff7c-118">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="0ff7c-119">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="0ff7c-119">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-allows-reading-numbers-as-strings](../../../includes/core-changes/serialization/5.0/jsonserializer-allows-reading-numbers-as-strings.md)]

***

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

<span data-ttu-id="0ff7c-120">\*\*_</span><span class="sxs-lookup"><span data-stu-id="0ff7c-120">\*\*_</span></span>

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

_*_

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

_*_

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

_*_

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

<span data-ttu-id="0ff7c-121">_\*\*</span><span class="sxs-lookup"><span data-stu-id="0ff7c-121">_\*\*</span></span>
