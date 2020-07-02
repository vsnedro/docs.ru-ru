---
ms.openlocfilehash: f8e5dee9e97956cea78b7c8ec999af1afe9ac66b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620649"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="13ee7-101">Параметр MinFreeMemoryPercentageToActiveService теперь учитывается</span><span class="sxs-lookup"><span data-stu-id="13ee7-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="13ee7-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="13ee7-102">Details</span></span>

<span data-ttu-id="13ee7-103">Этот параметр задает минимальный объем памяти, который должен быть доступен на сервере перед активацией службы WCF.</span><span class="sxs-lookup"><span data-stu-id="13ee7-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="13ee7-104">Он предназначен для предотвращения исключений <xref:System.OutOfMemoryException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="13ee7-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="13ee7-105">В .NET Framework 4.5 этот параметр не оказывал никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="13ee7-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="13ee7-106">В .NET Framework 4.5.1 этот параметр уже используется.</span><span class="sxs-lookup"><span data-stu-id="13ee7-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="13ee7-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="13ee7-107">Suggestion</span></span>

<span data-ttu-id="13ee7-108">Исключение возникает, если объем свободной памяти на веб-сервере меньше процентного значения, заданного параметром конфигурации.</span><span class="sxs-lookup"><span data-stu-id="13ee7-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="13ee7-109">Некоторые службы WCF, которые успешно запускались и выполнялись в условиях ограниченной памяти, теперь могут завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="13ee7-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="13ee7-110">name</span><span class="sxs-lookup"><span data-stu-id="13ee7-110">Name</span></span>    | <span data-ttu-id="13ee7-111">Значение</span><span class="sxs-lookup"><span data-stu-id="13ee7-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="13ee7-112">Область</span><span class="sxs-lookup"><span data-stu-id="13ee7-112">Scope</span></span>   |<span data-ttu-id="13ee7-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="13ee7-113">Minor</span></span>|
|<span data-ttu-id="13ee7-114">Version</span><span class="sxs-lookup"><span data-stu-id="13ee7-114">Version</span></span>|<span data-ttu-id="13ee7-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="13ee7-115">4.5.1</span></span>|
|<span data-ttu-id="13ee7-116">Type</span><span class="sxs-lookup"><span data-stu-id="13ee7-116">Type</span></span>|<span data-ttu-id="13ee7-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="13ee7-117">Runtime</span></span>|
