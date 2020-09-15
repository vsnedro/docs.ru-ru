---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617547"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="34b28-101">HttpRuntime.AppDomainAppPath создает исключение NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="34b28-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="34b28-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="34b28-102">Details</span></span>

<span data-ttu-id="34b28-103">В платформе .NET Framework 4.6.2 среда выполнения создает исключение `T:System.NullReferenceException` при получении значения `P:System.Web.HttpRuntime.AppDomainAppPath`, которое содержит нуль-символы. В .NET Framework 4.6.1 и более ранних версий среда выполнения создает исключение `T:System.ArgumentNullException`.</span><span class="sxs-lookup"><span data-stu-id="34b28-103">In the .NET Framework 4.6.2, the runtime throws a `T:System.NullReferenceException` when retrieving a `P:System.Web.HttpRuntime.AppDomainAppPath` value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an `T:System.ArgumentNullException`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="34b28-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="34b28-104">Suggestion</span></span>

<span data-ttu-id="34b28-105">В ответ на это изменение можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="34b28-105">You can do either of the follow to respond to this change:</span></span>

- <span data-ttu-id="34b28-106">обрабатывайте `T:System.NullReferenceException`, если приложение работает на платформе .NET Framework 4.6.2;</span><span class="sxs-lookup"><span data-stu-id="34b28-106">Handle the `T:System.NullReferenceException` if you application is running on the .NET Framework 4.6.2.</span></span>
- <span data-ttu-id="34b28-107">обновите систему до версии .NET Framework 4.7, в которой восстановлено прежнее поведение, то есть создается исключение `T:System.ArgumentNullException`.</span><span class="sxs-lookup"><span data-stu-id="34b28-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an `T:System.ArgumentNullException`.</span></span>

| <span data-ttu-id="34b28-108">name</span><span class="sxs-lookup"><span data-stu-id="34b28-108">Name</span></span>    | <span data-ttu-id="34b28-109">Значение</span><span class="sxs-lookup"><span data-stu-id="34b28-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="34b28-110">Область</span><span class="sxs-lookup"><span data-stu-id="34b28-110">Scope</span></span>   | <span data-ttu-id="34b28-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="34b28-111">Edge</span></span>        |
| <span data-ttu-id="34b28-112">Version</span><span class="sxs-lookup"><span data-stu-id="34b28-112">Version</span></span> | <span data-ttu-id="34b28-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="34b28-113">4.6.2</span></span>       |
| <span data-ttu-id="34b28-114">Type</span><span class="sxs-lookup"><span data-stu-id="34b28-114">Type</span></span>    | <span data-ttu-id="34b28-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="34b28-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="34b28-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="34b28-116">Affected APIs</span></span>

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>
