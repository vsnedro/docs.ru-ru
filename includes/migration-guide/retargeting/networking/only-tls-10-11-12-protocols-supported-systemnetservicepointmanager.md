---
ms.openlocfilehash: 87dc93ece10eaedbfbabddb5f857d0bcd12e05c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615761"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a><span data-ttu-id="929b6-101">В System.Net.ServicePointManager и System.Net.Security.SslStream поддерживаются только протоколы Tls 1.0, 1.1 и 1.2</span><span class="sxs-lookup"><span data-stu-id="929b6-101">Only Tls 1.0, 1.1 and 1.2 protocols supported in System.Net.ServicePointManager and System.Net.Security.SslStream</span></span>

#### <a name="details"></a><span data-ttu-id="929b6-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="929b6-102">Details</span></span>

<span data-ttu-id="929b6-103">Начиная с версии .NET Framework 4.6, классы <xref:System.Net.ServicePointManager> и <xref:System.Net.Security.SslStream> могут использовать только один из трех протоколов: Tls1.0, Tls1.1 или Tls1.2.</span><span class="sxs-lookup"><span data-stu-id="929b6-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager> and <xref:System.Net.Security.SslStream> classes are only allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="929b6-104">Протокол SSL 3.0 и шифрование RC4 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="929b6-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="929b6-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="929b6-105">Suggestion</span></span>

<span data-ttu-id="929b6-106">Рекомендуется обновить приложения на стороне сервера для использования Tls1.0, Tls1.1 или Tls1.2.</span><span class="sxs-lookup"><span data-stu-id="929b6-106">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="929b6-107">Если это невозможно, или если клиентские приложения не работают, можно использовать класс <xref:System.AppContext?displayProperty=fullName>, чтобы отказаться от этой функции одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="929b6-107">If this is not feasible, or if client apps are broken, the <xref:System.AppContext?displayProperty=fullName> class can be used to opt out of this feature in either of two ways:</span></span>

- <span data-ttu-id="929b6-108">Путем программной установки параметров совместимости в <xref:System.AppContext?displayProperty=fullName>, как описано [здесь](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span><span class="sxs-lookup"><span data-stu-id="929b6-108">By programmatically setting compat switches on the <xref:System.AppContext?displayProperty=fullName>, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="929b6-109">путем добавления следующей строки в раздел `<runtime>` файла app.config:</span><span class="sxs-lookup"><span data-stu-id="929b6-109">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>
```

| <span data-ttu-id="929b6-110">name</span><span class="sxs-lookup"><span data-stu-id="929b6-110">Name</span></span>    | <span data-ttu-id="929b6-111">Значение</span><span class="sxs-lookup"><span data-stu-id="929b6-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="929b6-112">Область</span><span class="sxs-lookup"><span data-stu-id="929b6-112">Scope</span></span>   | <span data-ttu-id="929b6-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="929b6-113">Minor</span></span>       |
| <span data-ttu-id="929b6-114">Version</span><span class="sxs-lookup"><span data-stu-id="929b6-114">Version</span></span> | <span data-ttu-id="929b6-115">4.6</span><span class="sxs-lookup"><span data-stu-id="929b6-115">4.6</span></span>         |
| <span data-ttu-id="929b6-116">Type</span><span class="sxs-lookup"><span data-stu-id="929b6-116">Type</span></span>    | <span data-ttu-id="929b6-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="929b6-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="929b6-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="929b6-118">Affected APIs</span></span>

- <xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType>
