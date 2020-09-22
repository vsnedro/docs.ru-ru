---
ms.openlocfilehash: 3cf1740565343558a85fdfa68957773468c28231
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770933"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="c1e8f-101">WCF PipeConnection.GetHashAlgorithm теперь использует SHA256</span><span class="sxs-lookup"><span data-stu-id="c1e8f-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="c1e8f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c1e8f-102">Details</span></span>

<span data-ttu-id="c1e8f-103">Начиная с версии .NET Framework 4.7.1 Windows Communication Foundation использует хэш SHA256 для формирования случайных имен для именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="c1e8f-104">В .NET Framework 4.7 и более ранних версиях используется хэш SHA-1.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c1e8f-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="c1e8f-105">Suggestion</span></span>

<span data-ttu-id="c1e8f-106">Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел `<runtime>` файла app.config:</span><span class="sxs-lookup"><span data-stu-id="c1e8f-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
  </runtime>
</configuration>

| Name    | Value   |
|:--------|:--------|
| Scope   | Minor   |
| Version | 4.7.1   |
| Type    | Runtime |

#### Affected APIs

Not detectable via API analysis.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
