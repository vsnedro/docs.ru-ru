---
ms.openlocfilehash: 26c50ac8b0e570e31a38b1913f73acbe21fae08b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497406"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a><span data-ttu-id="a400f-101">AppDomainSetup.DynamicBase больше не задается случайно с помощью UseRandomizedStringHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="a400f-101">AppDomainSetup.DynamicBase is no longer randomized by UseRandomizedStringHashAlgorithm</span></span>

#### <a name="details"></a><span data-ttu-id="a400f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="a400f-102">Details</span></span>

<span data-ttu-id="a400f-103">В версиях до .NET Framework 4.6 значение <xref:System.AppDomainSetup.DynamicBase> задавалось случайным образом между доменами приложений или между процессами, если в файле конфигурации приложения был включен UseRandomizedStringHashAlgorithm.</span><span class="sxs-lookup"><span data-stu-id="a400f-103">Prior to the .NET Framework 4.6, the value of <xref:System.AppDomainSetup.DynamicBase> would be randomized between application domains, or between processes, if UseRandomizedStringHashAlgorithm was enabled in the app's config file.</span></span> <span data-ttu-id="a400f-104">Начиная с версии .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> будет возвращать постоянный результат между различными выполняющимися экземплярами приложения и между различными доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="a400f-104">Beginning in the .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> will return a stable result between different instances of an app running, and between different app domains.</span></span> <span data-ttu-id="a400f-105">Динамические основания при этом по-прежнему будут различаться для разных приложений. Это изменение исключает только случайный элемент именования для различных экземпляров одного приложения.</span><span class="sxs-lookup"><span data-stu-id="a400f-105">Dynamic bases will still differ for different apps; this change only removes the random naming element for different instances of the same app.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a400f-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="a400f-106">Suggestion</span></span>

<span data-ttu-id="a400f-107">Обратите внимание, что включение <code>UseRandomizedStringHashAlgorithm</code> не приведет к случайной установке <xref:System.AppDomainSetup.DynamicBase>.</span><span class="sxs-lookup"><span data-stu-id="a400f-107">Be aware that enabling <code>UseRandomizedStringHashAlgorithm</code> will not result in <xref:System.AppDomainSetup.DynamicBase> being randomized.</span></span> <span data-ttu-id="a400f-108">Если требуется случайное основание, для его получения необходимо использовать код приложения, а не этот API.</span><span class="sxs-lookup"><span data-stu-id="a400f-108">If a random base is needed, it must be produced in your app's code rather than via this API.</span></span>

| <span data-ttu-id="a400f-109">name</span><span class="sxs-lookup"><span data-stu-id="a400f-109">Name</span></span>    | <span data-ttu-id="a400f-110">Значение</span><span class="sxs-lookup"><span data-stu-id="a400f-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a400f-111">Область</span><span class="sxs-lookup"><span data-stu-id="a400f-111">Scope</span></span>   |<span data-ttu-id="a400f-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="a400f-112">Edge</span></span>|
|<span data-ttu-id="a400f-113">Version</span><span class="sxs-lookup"><span data-stu-id="a400f-113">Version</span></span>|<span data-ttu-id="a400f-114">4.6</span><span class="sxs-lookup"><span data-stu-id="a400f-114">4.6</span></span>|
|<span data-ttu-id="a400f-115">Type</span><span class="sxs-lookup"><span data-stu-id="a400f-115">Type</span></span>|<span data-ttu-id="a400f-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="a400f-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a400f-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="a400f-117">Affected APIs</span></span>

- <xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.AppDomainSetup.DynamicBase`

-->
