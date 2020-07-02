---
ms.openlocfilehash: 08ad6fd4ccb6d5ddbbb4fa7ef1b325ce30689748
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621414"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a><span data-ttu-id="6bb6c-101">AppDomainSetup.DynamicBase больше не задается случайно с помощью UseRandomizedStringHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="6bb6c-101">AppDomainSetup.DynamicBase is no longer randomized by UseRandomizedStringHashAlgorithm</span></span>

#### <a name="details"></a><span data-ttu-id="6bb6c-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="6bb6c-102">Details</span></span>

<span data-ttu-id="6bb6c-103">В версиях до .NET Framework 4.6 значение <xref:System.AppDomainSetup.DynamicBase> задавалось случайным образом между доменами приложений или между процессами, если в файле конфигурации приложения был включен UseRandomizedStringHashAlgorithm.</span><span class="sxs-lookup"><span data-stu-id="6bb6c-103">Prior to the .NET Framework 4.6, the value of <xref:System.AppDomainSetup.DynamicBase> would be randomized between application domains, or between processes, if UseRandomizedStringHashAlgorithm was enabled in the app's config file.</span></span> <span data-ttu-id="6bb6c-104">Начиная с версии .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> будет возвращать постоянный результат между различными выполняющимися экземплярами приложения и между различными доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="6bb6c-104">Beginning in the .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> will return a stable result between different instances of an app running, and between different app domains.</span></span> <span data-ttu-id="6bb6c-105">Динамические основания при этом по-прежнему будут различаться для разных приложений. Это изменение исключает только случайный элемент именования для различных экземпляров одного приложения.</span><span class="sxs-lookup"><span data-stu-id="6bb6c-105">Dynamic bases will still differ for different apps; this change only removes the random naming element for different instances of the same app.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6bb6c-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="6bb6c-106">Suggestion</span></span>

<span data-ttu-id="6bb6c-107">Обратите внимание, что включение <code>UseRandomizedStringHashAlgorithm</code> не приведет к случайной установке <xref:System.AppDomainSetup.DynamicBase>.</span><span class="sxs-lookup"><span data-stu-id="6bb6c-107">Be aware that enabling <code>UseRandomizedStringHashAlgorithm</code> will not result in <xref:System.AppDomainSetup.DynamicBase> being randomized.</span></span> <span data-ttu-id="6bb6c-108">Если требуется случайное основание, для его получения необходимо использовать код приложения, а не этот API.</span><span class="sxs-lookup"><span data-stu-id="6bb6c-108">If a random base is needed, it must be produced in your app's code rather than via this API.</span></span>

| <span data-ttu-id="6bb6c-109">name</span><span class="sxs-lookup"><span data-stu-id="6bb6c-109">Name</span></span>    | <span data-ttu-id="6bb6c-110">Значение</span><span class="sxs-lookup"><span data-stu-id="6bb6c-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6bb6c-111">Область</span><span class="sxs-lookup"><span data-stu-id="6bb6c-111">Scope</span></span>   |<span data-ttu-id="6bb6c-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="6bb6c-112">Edge</span></span>|
|<span data-ttu-id="6bb6c-113">Version</span><span class="sxs-lookup"><span data-stu-id="6bb6c-113">Version</span></span>|<span data-ttu-id="6bb6c-114">4.6</span><span class="sxs-lookup"><span data-stu-id="6bb6c-114">4.6</span></span>|
|<span data-ttu-id="6bb6c-115">Type</span><span class="sxs-lookup"><span data-stu-id="6bb6c-115">Type</span></span>|<span data-ttu-id="6bb6c-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="6bb6c-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6bb6c-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="6bb6c-117">Affected APIs</span></span>

-<xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
