---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770881"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="f2cf2-101">MsmqSecureHashAlgorithm WCF теперь по умолчанию имеет значение SHA256</span><span class="sxs-lookup"><span data-stu-id="f2cf2-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="f2cf2-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f2cf2-102">Details</span></span>

<span data-ttu-id="f2cf2-103">Начиная с версии .NET Framework 4.7.1, в WCF для подписывания сообщений Msmq по умолчанию используется алгоритм SHA256.</span><span class="sxs-lookup"><span data-stu-id="f2cf2-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="f2cf2-104">В .NET Framework 4.7 и более ранних версий для подписывания сообщений по умолчанию используется алгоритм SHA1.</span><span class="sxs-lookup"><span data-stu-id="f2cf2-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f2cf2-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="f2cf2-105">Suggestion</span></span>

<span data-ttu-id="f2cf2-106">Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел `<runtime>` файла app.config:</span><span class="sxs-lookup"><span data-stu-id="f2cf2-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the `<runtime>` section of your app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| <span data-ttu-id="f2cf2-107">name</span><span class="sxs-lookup"><span data-stu-id="f2cf2-107">Name</span></span>    | <span data-ttu-id="f2cf2-108">Значение</span><span class="sxs-lookup"><span data-stu-id="f2cf2-108">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="f2cf2-109">Область</span><span class="sxs-lookup"><span data-stu-id="f2cf2-109">Scope</span></span>   | <span data-ttu-id="f2cf2-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="f2cf2-110">Minor</span></span>   |
| <span data-ttu-id="f2cf2-111">Версия</span><span class="sxs-lookup"><span data-stu-id="f2cf2-111">Version</span></span> | <span data-ttu-id="f2cf2-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="f2cf2-112">4.7.1</span></span>   |
| <span data-ttu-id="f2cf2-113">Type</span><span class="sxs-lookup"><span data-stu-id="f2cf2-113">Type</span></span>    | <span data-ttu-id="f2cf2-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f2cf2-114">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="f2cf2-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f2cf2-115">Affected APIs</span></span>

<span data-ttu-id="f2cf2-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="f2cf2-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
