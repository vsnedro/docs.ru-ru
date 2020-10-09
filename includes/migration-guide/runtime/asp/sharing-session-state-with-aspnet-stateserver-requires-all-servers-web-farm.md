---
ms.openlocfilehash: e450c53008e7562e37518fdfd6872ff9b63b6ac3
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609142"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="9c5a1-101">Для совместного доступа к состоянию сеанса с ASP.NET StateServer все серверы на веб-ферме должны использовать одинаковую версию .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c5a1-101">Sharing session state with ASP.NET StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="9c5a1-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="9c5a1-102">Details</span></span>

<span data-ttu-id="9c5a1-103">При включении состояния сеанса <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> все серверы на данной веб-ферме должны использовать одинаковую версию платформы .NET Framework, чтобы состояние передавалось должным образом.</span><span class="sxs-lookup"><span data-stu-id="9c5a1-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9c5a1-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="9c5a1-104">Suggestion</span></span>

<span data-ttu-id="9c5a1-105">Обновите версии платформы .NET Framework на веб-серверах, которые совместно и одновременно используют состояние.</span><span class="sxs-lookup"><span data-stu-id="9c5a1-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="9c5a1-106">name</span><span class="sxs-lookup"><span data-stu-id="9c5a1-106">Name</span></span>    | <span data-ttu-id="9c5a1-107">Значение</span><span class="sxs-lookup"><span data-stu-id="9c5a1-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9c5a1-108">Область</span><span class="sxs-lookup"><span data-stu-id="9c5a1-108">Scope</span></span>   |<span data-ttu-id="9c5a1-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="9c5a1-109">Edge</span></span>|
|<span data-ttu-id="9c5a1-110">Version</span><span class="sxs-lookup"><span data-stu-id="9c5a1-110">Version</span></span>|<span data-ttu-id="9c5a1-111">4.5</span><span class="sxs-lookup"><span data-stu-id="9c5a1-111">4.5</span></span>|
|<span data-ttu-id="9c5a1-112">Type</span><span class="sxs-lookup"><span data-stu-id="9c5a1-112">Type</span></span>|<span data-ttu-id="9c5a1-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="9c5a1-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9c5a1-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="9c5a1-114">Affected APIs</span></span>

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
