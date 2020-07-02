---
ms.openlocfilehash: f955e270f709ddf6eea2e44bbcf386e372b9f6e3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621426"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a><span data-ttu-id="e2874-101">TargetFrameworkName для домена приложения по умолчанию больше не принимает значение NULL по умолчанию, если оно не задано</span><span class="sxs-lookup"><span data-stu-id="e2874-101">TargetFrameworkName for default app domain no longer defaults to null if not set</span></span>

#### <a name="details"></a><span data-ttu-id="e2874-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e2874-102">Details</span></span>

<span data-ttu-id="e2874-103">Свойство <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> имело ранее значение NULL в домене приложения по умолчанию, если оно не было задано явно.</span><span class="sxs-lookup"><span data-stu-id="e2874-103">The <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> was previously null in the default app domain, unless it was explicitly set.</span></span> <span data-ttu-id="e2874-104">Начиная с версии 4.6, свойство <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> для домена приложения по умолчанию будет иметь значение по умолчанию, полученное из свойства TargetFrameworkAttribute (если оно доступно).</span><span class="sxs-lookup"><span data-stu-id="e2874-104">Beginning in 4.6, the <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> property for the default app domain will have a default value derived from the TargetFrameworkAttribute (if one is present).</span></span> <span data-ttu-id="e2874-105">Домены приложений не по умолчанию будут по-прежнему наследовать свойство <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> от домена приложения по умолчанию (который не будет по умолчанию иметь значение NULL в 4.6), если оно явно не переопределено.</span><span class="sxs-lookup"><span data-stu-id="e2874-105">Non-default app domains will continue to inherit their <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> from the default app domain (which will not default to null in 4.6) unless it is explicitly overridden.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e2874-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="e2874-106">Suggestion</span></span>

<span data-ttu-id="e2874-107">Следует обновить код так, чтобы он не зависел от <xref:System.AppDomainSetup.TargetFrameworkName>, принимающего п умолчанию значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e2874-107">Code should be updated to not depend on <xref:System.AppDomainSetup.TargetFrameworkName> defaulting to null.</span></span> <span data-ttu-id="e2874-108">Если требуется, чтобы свойство продолжало принимать значение NULL, ему можно явно присвоить это значение.</span><span class="sxs-lookup"><span data-stu-id="e2874-108">If it is required that this property continue to evaluate to null, it can be explicitly set to that value.</span></span>

| <span data-ttu-id="e2874-109">name</span><span class="sxs-lookup"><span data-stu-id="e2874-109">Name</span></span>    | <span data-ttu-id="e2874-110">Значение</span><span class="sxs-lookup"><span data-stu-id="e2874-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e2874-111">Область</span><span class="sxs-lookup"><span data-stu-id="e2874-111">Scope</span></span>   |<span data-ttu-id="e2874-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="e2874-112">Edge</span></span>|
|<span data-ttu-id="e2874-113">Version</span><span class="sxs-lookup"><span data-stu-id="e2874-113">Version</span></span>|<span data-ttu-id="e2874-114">4.6</span><span class="sxs-lookup"><span data-stu-id="e2874-114">4.6</span></span>|
|<span data-ttu-id="e2874-115">Type</span><span class="sxs-lookup"><span data-stu-id="e2874-115">Type</span></span>|<span data-ttu-id="e2874-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e2874-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e2874-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e2874-117">Affected APIs</span></span>

-<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType></li></ul>|
