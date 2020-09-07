---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497191"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="b7cd2-101">Параметр MinFreeMemoryPercentageToActiveService теперь учитывается</span><span class="sxs-lookup"><span data-stu-id="b7cd2-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="b7cd2-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b7cd2-102">Details</span></span>

<span data-ttu-id="b7cd2-103">Этот параметр задает минимальный объем памяти, который должен быть доступен на сервере перед активацией службы WCF.</span><span class="sxs-lookup"><span data-stu-id="b7cd2-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="b7cd2-104">Он предназначен для предотвращения исключений <xref:System.OutOfMemoryException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="b7cd2-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="b7cd2-105">В .NET Framework 4.5 этот параметр не оказывал никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="b7cd2-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="b7cd2-106">В .NET Framework 4.5.1 этот параметр уже используется.</span><span class="sxs-lookup"><span data-stu-id="b7cd2-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b7cd2-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="b7cd2-107">Suggestion</span></span>

<span data-ttu-id="b7cd2-108">Исключение возникает, если объем свободной памяти на веб-сервере меньше процентного значения, заданного параметром конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b7cd2-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="b7cd2-109">Некоторые службы WCF, которые успешно запускались и выполнялись в условиях ограниченной памяти, теперь могут завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b7cd2-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="b7cd2-110">name</span><span class="sxs-lookup"><span data-stu-id="b7cd2-110">Name</span></span>    | <span data-ttu-id="b7cd2-111">Значение</span><span class="sxs-lookup"><span data-stu-id="b7cd2-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b7cd2-112">Область</span><span class="sxs-lookup"><span data-stu-id="b7cd2-112">Scope</span></span>   |<span data-ttu-id="b7cd2-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="b7cd2-113">Minor</span></span>|
|<span data-ttu-id="b7cd2-114">Version</span><span class="sxs-lookup"><span data-stu-id="b7cd2-114">Version</span></span>|<span data-ttu-id="b7cd2-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="b7cd2-115">4.5.1</span></span>|
|<span data-ttu-id="b7cd2-116">Type</span><span class="sxs-lookup"><span data-stu-id="b7cd2-116">Type</span></span>|<span data-ttu-id="b7cd2-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="b7cd2-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b7cd2-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b7cd2-118">Affected APIs</span></span>

<span data-ttu-id="b7cd2-119">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="b7cd2-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
