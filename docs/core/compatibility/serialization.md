---
title: Критические изменения в категории сериализации
description: Перечень критических изменений в категории сериализации в .NET Core и .NET 5.0 и более поздних версий.
ms.date: 07/30/2020
ms.openlocfilehash: f635ff2cd233922a0bbb327de23c8bf25d344fa0
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517414"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="62e13-103">Критические изменения в категории сериализации</span><span class="sxs-lookup"><span data-stu-id="62e13-103">Serialization breaking changes</span></span>

<span data-ttu-id="62e13-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="62e13-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="62e13-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="62e13-105">Breaking change</span></span> | <span data-ttu-id="62e13-106">Представленные версии</span><span class="sxs-lookup"><span data-stu-id="62e13-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="62e13-107">Метод BinaryFormatter.Deserialize повторно изолирует некоторые исключения в классе SerializationException</span><span class="sxs-lookup"><span data-stu-id="62e13-107">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="62e13-108">5.0</span><span class="sxs-lookup"><span data-stu-id="62e13-108">5.0</span></span> |

## <a name="net-core-50"></a><span data-ttu-id="62e13-109">.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="62e13-109">.NET Core 5.0</span></span>

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
