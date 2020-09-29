---
ms.openlocfilehash: 9f5f238e3d4222af1da3a1713e1b3e65de6e6f49
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "91025122"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="2c064-101">WCF PipeConnection.GetHashAlgorithm теперь использует SHA256</span><span class="sxs-lookup"><span data-stu-id="2c064-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="2c064-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2c064-102">Details</span></span>

<span data-ttu-id="2c064-103">Начиная с версии .NET Framework 4.7.1 Windows Communication Foundation использует хэш SHA256 для формирования случайных имен для именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="2c064-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="2c064-104">В .NET Framework 4.7 и более ранних версиях используется хэш SHA-1.</span><span class="sxs-lookup"><span data-stu-id="2c064-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2c064-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="2c064-105">Suggestion</span></span>

<span data-ttu-id="2c064-106">Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел `<runtime>` файла app.config:</span><span class="sxs-lookup"><span data-stu-id="2c064-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="2c064-107">name</span><span class="sxs-lookup"><span data-stu-id="2c064-107">Name</span></span>    | <span data-ttu-id="2c064-108">Значение</span><span class="sxs-lookup"><span data-stu-id="2c064-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="2c064-109">Область</span><span class="sxs-lookup"><span data-stu-id="2c064-109">Scope</span></span>   | <span data-ttu-id="2c064-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="2c064-110">Minor</span></span>   |
| <span data-ttu-id="2c064-111">Версия</span><span class="sxs-lookup"><span data-stu-id="2c064-111">Version</span></span> | <span data-ttu-id="2c064-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="2c064-112">4.7.1</span></span>   |
| <span data-ttu-id="2c064-113">Type</span><span class="sxs-lookup"><span data-stu-id="2c064-113">Type</span></span>    | <span data-ttu-id="2c064-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="2c064-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2c064-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2c064-115">Affected APIs</span></span>

<span data-ttu-id="2c064-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="2c064-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
