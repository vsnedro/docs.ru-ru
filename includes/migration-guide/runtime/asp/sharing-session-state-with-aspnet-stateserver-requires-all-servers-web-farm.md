---
ms.openlocfilehash: 76425ca03c98cd6a23b8366257f9e0d53b486edb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497455"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="7c2b4-101">Для совместного доступа к состоянию сеанса с Asp.Net StateServer все серверы на веб-ферме должны использовать одинаковую версию .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7c2b4-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="7c2b4-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="7c2b4-102">Details</span></span>

<span data-ttu-id="7c2b4-103">При включении состояния сеанса <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> все серверы на данной веб-ферме должны использовать одинаковую версию платформы .NET Framework, чтобы состояние передавалось должным образом.</span><span class="sxs-lookup"><span data-stu-id="7c2b4-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7c2b4-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="7c2b4-104">Suggestion</span></span>

<span data-ttu-id="7c2b4-105">Обновите версии платформы .NET Framework на веб-серверах, которые совместно и одновременно используют состояние.</span><span class="sxs-lookup"><span data-stu-id="7c2b4-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="7c2b4-106">name</span><span class="sxs-lookup"><span data-stu-id="7c2b4-106">Name</span></span>    | <span data-ttu-id="7c2b4-107">Значение</span><span class="sxs-lookup"><span data-stu-id="7c2b4-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7c2b4-108">Область</span><span class="sxs-lookup"><span data-stu-id="7c2b4-108">Scope</span></span>   |<span data-ttu-id="7c2b4-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="7c2b4-109">Edge</span></span>|
|<span data-ttu-id="7c2b4-110">Version</span><span class="sxs-lookup"><span data-stu-id="7c2b4-110">Version</span></span>|<span data-ttu-id="7c2b4-111">4.5</span><span class="sxs-lookup"><span data-stu-id="7c2b4-111">4.5</span></span>|
|<span data-ttu-id="7c2b4-112">Type</span><span class="sxs-lookup"><span data-stu-id="7c2b4-112">Type</span></span>|<span data-ttu-id="7c2b4-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="7c2b4-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7c2b4-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="7c2b4-114">Affected APIs</span></span>

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
