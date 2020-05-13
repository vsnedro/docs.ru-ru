---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859637"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a><span data-ttu-id="3fb98-101">WebClient.CancelAsync не всегда сразу отменяет запрос</span><span class="sxs-lookup"><span data-stu-id="3fb98-101">WebClient.CancelAsync doesn't always cancel immediately</span></span>

<span data-ttu-id="3fb98-102">Начиная с .NET Core 2.0 вызов <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> не отменяет запрос сразу, если ответ начал поступать.</span><span class="sxs-lookup"><span data-stu-id="3fb98-102">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> doesn't cancel the request immediately if the response has started to fetch.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3fb98-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="3fb98-103">Change description</span></span>

<span data-ttu-id="3fb98-104">Ранее вызов <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> отменял запрос сразу.</span><span class="sxs-lookup"><span data-stu-id="3fb98-104">Previously, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> canceled the request immediately.</span></span> <span data-ttu-id="3fb98-105">Начиная с .NET Core 2.0 вызов <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> отменяет запрос сразу, только если ответ не начал поступать.</span><span class="sxs-lookup"><span data-stu-id="3fb98-105">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> cancels the request immediately only if the response hasn't started fetching.</span></span> <span data-ttu-id="3fb98-106">Если ответ начал поступать, запрос отменяется только после считывания полного ответа.</span><span class="sxs-lookup"><span data-stu-id="3fb98-106">If the response has started to fetch, the request is cancelled only after a complete response is read.</span></span>

<span data-ttu-id="3fb98-107">Это изменение было реализовано, так как API <xref:System.Net.WebClient> является нерекомендуемым и заменен на <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="3fb98-107">This change was implemented because the <xref:System.Net.WebClient> API is deprecated in favor of <xref:System.Net.Http.HttpClient>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3fb98-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="3fb98-108">Version introduced</span></span>

<span data-ttu-id="3fb98-109">2.0</span><span class="sxs-lookup"><span data-stu-id="3fb98-109">2.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3fb98-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="3fb98-110">Recommended action</span></span>

<span data-ttu-id="3fb98-111">Используйте класс <xref:System.Net.Http.HttpClient?displayProperty=fullName> вместо <xref:System.Net.WebClient?displayProperty=fullName>, который является нерекомендуемым.</span><span class="sxs-lookup"><span data-stu-id="3fb98-111">Use the <xref:System.Net.Http.HttpClient?displayProperty=fullName> class instead of <xref:System.Net.WebClient?displayProperty=fullName>, which is deprecated.</span></span>

#### <a name="category"></a><span data-ttu-id="3fb98-112">Категория</span><span class="sxs-lookup"><span data-stu-id="3fb98-112">Category</span></span>

<span data-ttu-id="3fb98-113">Сети</span><span class="sxs-lookup"><span data-stu-id="3fb98-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3fb98-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="3fb98-114">Affected APIs</span></span>

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
