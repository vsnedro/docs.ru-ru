---
title: Критические изменения сети
description: Список критических изменений сети в .NET Core.
ms.date: 05/05/2020
ms.openlocfilehash: fdbd3f3bdcae5048b4f01e4d827f8a0e876c5c15
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050531"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="864f0-103">Критические изменения сети</span><span class="sxs-lookup"><span data-stu-id="864f0-103">Networking breaking changes</span></span>

<span data-ttu-id="864f0-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="864f0-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="864f0-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="864f0-105">Breaking change</span></span> | <span data-ttu-id="864f0-106">Представленные версии</span><span class="sxs-lookup"><span data-stu-id="864f0-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="864f0-107">NegotiateStream и SslStream поддерживают последовательные операции Begin</span><span class="sxs-lookup"><span data-stu-id="864f0-107">NegotiateStream and SslStream allow successive Begin operations</span></span>](#negotiatestream-and-sslstream-allow-successive-begin-operations) | <span data-ttu-id="864f0-108">5,0</span><span class="sxs-lookup"><span data-stu-id="864f0-108">5.0</span></span> |
| [<span data-ttu-id="864f0-109">Socket.LocalEndPoint обновляется после вызова SendToAsync</span><span class="sxs-lookup"><span data-stu-id="864f0-109">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>](#socketlocalendpoint-is-updated-after-calling-sendtoasync) | <span data-ttu-id="864f0-110">5,0</span><span class="sxs-lookup"><span data-stu-id="864f0-110">5.0</span></span> |
| [<span data-ttu-id="864f0-111">Класс WinHttpHandler удален из среды выполнения .NET</span><span class="sxs-lookup"><span data-stu-id="864f0-111">WinHttpHandler removed from .NET runtime</span></span>](#winhttphandler-removed-from-net-runtime) | <span data-ttu-id="864f0-112">5,0</span><span class="sxs-lookup"><span data-stu-id="864f0-112">5.0</span></span> |
| [<span data-ttu-id="864f0-113">MulticastOption.Group не принимает значение null</span><span class="sxs-lookup"><span data-stu-id="864f0-113">MulticastOption.Group doesn't accept a null value</span></span>](#multicastoptiongroup-doesnt-accept-a-null-value) | <span data-ttu-id="864f0-114">5,0</span><span class="sxs-lookup"><span data-stu-id="864f0-114">5.0</span></span> |
| [<span data-ttu-id="864f0-115">Алгоритмы обработки путей класса Cookie приведены в соответствие с RFC 6265</span><span class="sxs-lookup"><span data-stu-id="864f0-115">Cookie Path handling now conforms to RFC 6265</span></span>](#cookie-path-handling-now-conforms-to-rfc-6265) | <span data-ttu-id="864f0-116">5,0</span><span class="sxs-lookup"><span data-stu-id="864f0-116">5.0</span></span> |
| [<span data-ttu-id="864f0-117">Значение по умолчанию для параметра HttpRequestMessage.Version изменено на 1.1</span><span class="sxs-lookup"><span data-stu-id="864f0-117">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="864f0-118">3.0</span><span class="sxs-lookup"><span data-stu-id="864f0-118">3.0</span></span> |
| [<span data-ttu-id="864f0-119">WebClient.CancelAsync не всегда сразу отменяет запрос</span><span class="sxs-lookup"><span data-stu-id="864f0-119">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="864f0-120">2.0</span><span class="sxs-lookup"><span data-stu-id="864f0-120">2.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="864f0-121">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="864f0-121">.NET 5.0</span></span>

[!INCLUDE [negotiatestream-sslstream-dont-fail-on-successive-begin-calls](../../../includes/core-changes/networking/5.0/negotiatestream-sslstream-dont-fail-on-successive-begin-calls.md)]

***

[!INCLUDE [localendpoint-updated-on-sendtoasync](../../../includes/core-changes/networking/5.0/localendpoint-updated-on-sendtoasync.md)]

***

[!INCLUDE [winhttphandler-removed-from-runtime](../../../includes/core-changes/networking/5.0/winhttphandler-removed-from-runtime.md)]

***

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

[!INCLUDE [cookie-path-conforms-to-rfc6265](../../../includes/core-changes/networking/5.0/cookie-path-conforms-to-rfc6265.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="864f0-122">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="864f0-122">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="864f0-123">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="864f0-123">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
