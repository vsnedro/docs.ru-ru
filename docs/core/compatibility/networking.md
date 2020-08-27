---
title: Критические изменения сети
description: Список критических изменений сети в .NET Core.
ms.date: 05/05/2020
ms.openlocfilehash: 568d26bde43ccd6e19fbe2d947f576ef5f99450a
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608478"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="67713-103">Критические изменения сети</span><span class="sxs-lookup"><span data-stu-id="67713-103">Networking breaking changes</span></span>

<span data-ttu-id="67713-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="67713-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="67713-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="67713-105">Breaking change</span></span> | <span data-ttu-id="67713-106">Представленные версии</span><span class="sxs-lookup"><span data-stu-id="67713-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="67713-107">Класс WinHttpHandler удален из среды выполнения .NET</span><span class="sxs-lookup"><span data-stu-id="67713-107">WinHttpHandler removed from .NET runtime</span></span>](#winhttphandler-removed-from-net-runtime) | <span data-ttu-id="67713-108">5,0</span><span class="sxs-lookup"><span data-stu-id="67713-108">5.0</span></span> |
| [<span data-ttu-id="67713-109">MulticastOption.Group не принимает значение null</span><span class="sxs-lookup"><span data-stu-id="67713-109">MulticastOption.Group doesn't accept a null value</span></span>](#multicastoptiongroup-doesnt-accept-a-null-value) | <span data-ttu-id="67713-110">5,0</span><span class="sxs-lookup"><span data-stu-id="67713-110">5.0</span></span> |
| [<span data-ttu-id="67713-111">Значение по умолчанию для параметра HttpRequestMessage.Version изменено на 1.1</span><span class="sxs-lookup"><span data-stu-id="67713-111">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="67713-112">3.0</span><span class="sxs-lookup"><span data-stu-id="67713-112">3.0</span></span> |
| [<span data-ttu-id="67713-113">WebClient.CancelAsync не всегда сразу отменяет запрос</span><span class="sxs-lookup"><span data-stu-id="67713-113">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="67713-114">2.0</span><span class="sxs-lookup"><span data-stu-id="67713-114">2.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="67713-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="67713-115">.NET 5.0</span></span>

[!INCLUDE [winhttphandler-removed-from-runtime](../../../includes/core-changes/networking/5.0/winhttphandler-removed-from-runtime.md)]

***

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="67713-116">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="67713-116">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="67713-117">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="67713-117">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
