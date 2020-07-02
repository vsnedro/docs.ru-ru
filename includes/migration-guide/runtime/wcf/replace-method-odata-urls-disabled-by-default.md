---
ms.openlocfilehash: b2fcacdb02c411c4dcb12051bf0c6759faccdea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620666"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="86b35-101">Метод Replace в URL-адресах OData по умолчанию отключен</span><span class="sxs-lookup"><span data-stu-id="86b35-101">The Replace method in OData URLs is disabled by default</span></span>

#### <a name="details"></a><span data-ttu-id="86b35-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="86b35-102">Details</span></span>

<span data-ttu-id="86b35-103">Начиная с .NET Framework 4.5, метод Replace в URL-адресах OData по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="86b35-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="86b35-104">Если метод Replace OData отключен (теперь по умолчанию), все запросы пользователя, включая функции Replace (которые используются редко), завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="86b35-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="86b35-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="86b35-105">Suggestion</span></span>

<span data-ttu-id="86b35-106">Если необходим метод Replace (который используется редко), его можно включить в параметрах конфигурации (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="86b35-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span></span> <span data-ttu-id="86b35-107">Однако включенный метод Replace может открывать уязвимости системы безопасности, поэтому он должен использоваться только после тщательной проверки.</span><span class="sxs-lookup"><span data-stu-id="86b35-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>

| <span data-ttu-id="86b35-108">name</span><span class="sxs-lookup"><span data-stu-id="86b35-108">Name</span></span>    | <span data-ttu-id="86b35-109">Значение</span><span class="sxs-lookup"><span data-stu-id="86b35-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="86b35-110">Область</span><span class="sxs-lookup"><span data-stu-id="86b35-110">Scope</span></span>   |<span data-ttu-id="86b35-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="86b35-111">Edge</span></span>|
|<span data-ttu-id="86b35-112">Version</span><span class="sxs-lookup"><span data-stu-id="86b35-112">Version</span></span>|<span data-ttu-id="86b35-113">4.5</span><span class="sxs-lookup"><span data-stu-id="86b35-113">4.5</span></span>|
|<span data-ttu-id="86b35-114">Type</span><span class="sxs-lookup"><span data-stu-id="86b35-114">Type</span></span>|<span data-ttu-id="86b35-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="86b35-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="86b35-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="86b35-116">Affected APIs</span></span>

-<xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
