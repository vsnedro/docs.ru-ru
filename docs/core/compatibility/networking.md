---
title: Критические изменения сети
description: Список критических изменений сети в .NET Core.
ms.date: 05/05/2020
ms.openlocfilehash: fa5807c882c3bc6f66e8a27361ccc14254e90b3e
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465522"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="28c6e-103">Критические изменения сети</span><span class="sxs-lookup"><span data-stu-id="28c6e-103">Networking breaking changes</span></span>

<span data-ttu-id="28c6e-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="28c6e-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="28c6e-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="28c6e-105">Breaking change</span></span> | <span data-ttu-id="28c6e-106">Представленные версии</span><span class="sxs-lookup"><span data-stu-id="28c6e-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="28c6e-107">Класс WinHttpHandler удален из среды выполнения .NET</span><span class="sxs-lookup"><span data-stu-id="28c6e-107">WinHttpHandler removed from .NET runtime</span></span>](#winhttphandler-removed-from-net-runtime) | <span data-ttu-id="28c6e-108">5,0</span><span class="sxs-lookup"><span data-stu-id="28c6e-108">5.0</span></span> |
| [<span data-ttu-id="28c6e-109">MulticastOption.Group не принимает значение null</span><span class="sxs-lookup"><span data-stu-id="28c6e-109">MulticastOption.Group doesn't accept a null value</span></span>](#multicastoptiongroup-doesnt-accept-a-null-value) | <span data-ttu-id="28c6e-110">5,0</span><span class="sxs-lookup"><span data-stu-id="28c6e-110">5.0</span></span> |
| [<span data-ttu-id="28c6e-111">Алгоритмы обработки путей класса Cookie приведены в соответствие с RFC 6265</span><span class="sxs-lookup"><span data-stu-id="28c6e-111">Cookie Path handling now conforms to RFC 6265</span></span>](#cookie-path-handling-now-conforms-to-rfc-6265) | <span data-ttu-id="28c6e-112">5,0</span><span class="sxs-lookup"><span data-stu-id="28c6e-112">5.0</span></span> |
| [<span data-ttu-id="28c6e-113">Значение по умолчанию для параметра HttpRequestMessage.Version изменено на 1.1</span><span class="sxs-lookup"><span data-stu-id="28c6e-113">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="28c6e-114">3.0</span><span class="sxs-lookup"><span data-stu-id="28c6e-114">3.0</span></span> |
| [<span data-ttu-id="28c6e-115">WebClient.CancelAsync не всегда сразу отменяет запрос</span><span class="sxs-lookup"><span data-stu-id="28c6e-115">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="28c6e-116">2.0</span><span class="sxs-lookup"><span data-stu-id="28c6e-116">2.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="28c6e-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="28c6e-117">.NET 5.0</span></span>

[!INCLUDE [winhttphandler-removed-from-runtime](../../../includes/core-changes/networking/5.0/winhttphandler-removed-from-runtime.md)]

***

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

[!INCLUDE [cookie-path-conforms-to-rfc6265](../../../includes/core-changes/networking/5.0/cookie-path-conforms-to-rfc6265.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="28c6e-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="28c6e-118">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="28c6e-119">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="28c6e-119">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
