---
title: Критические изменения сети
description: Список критических изменений сети в .NET Core.
ms.date: 05/05/2020
ms.openlocfilehash: 07e0b2e062ce244cd6312bbe08bcc63db4c74347
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859623"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="9dee5-103">Критические изменения сети</span><span class="sxs-lookup"><span data-stu-id="9dee5-103">Networking breaking changes</span></span>

<span data-ttu-id="9dee5-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="9dee5-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="9dee5-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="9dee5-105">Breaking change</span></span> | <span data-ttu-id="9dee5-106">Представленные версии</span><span class="sxs-lookup"><span data-stu-id="9dee5-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="9dee5-107">Значение по умолчанию для параметра HttpRequestMessage.Version изменено на 1.1</span><span class="sxs-lookup"><span data-stu-id="9dee5-107">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="9dee5-108">3.0</span><span class="sxs-lookup"><span data-stu-id="9dee5-108">3.0</span></span> |
| [<span data-ttu-id="9dee5-109">WebClient.CancelAsync не всегда сразу отменяет запрос</span><span class="sxs-lookup"><span data-stu-id="9dee5-109">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="9dee5-110">2.0</span><span class="sxs-lookup"><span data-stu-id="9dee5-110">2.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="9dee5-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9dee5-111">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="9dee5-112">.NET Core 2.0;</span><span class="sxs-lookup"><span data-stu-id="9dee5-112">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
