---
ms.openlocfilehash: 0f87f9e9b87860da97ce96e18104b44ec4327c91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621228"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="9273d-101">WCF PipeConnection.GetHashAlgorithm теперь использует SHA256</span><span class="sxs-lookup"><span data-stu-id="9273d-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="9273d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="9273d-102">Details</span></span>

<span data-ttu-id="9273d-103">Начиная с версии .NET Framework 4.7.1 Windows Communication Foundation использует хэш SHA256 для формирования случайных имен для именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="9273d-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="9273d-104">В .NET Framework 4.7 и более ранних версиях используется хэш SHA-1.</span><span class="sxs-lookup"><span data-stu-id="9273d-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9273d-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="9273d-105">Suggestion</span></span>

<span data-ttu-id="9273d-106">Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config:</span><span class="sxs-lookup"><span data-stu-id="9273d-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="9273d-107">name</span><span class="sxs-lookup"><span data-stu-id="9273d-107">Name</span></span>    | <span data-ttu-id="9273d-108">Значение</span><span class="sxs-lookup"><span data-stu-id="9273d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9273d-109">Область</span><span class="sxs-lookup"><span data-stu-id="9273d-109">Scope</span></span>   |<span data-ttu-id="9273d-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="9273d-110">Minor</span></span>|
|<span data-ttu-id="9273d-111">Версия</span><span class="sxs-lookup"><span data-stu-id="9273d-111">Version</span></span>|<span data-ttu-id="9273d-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="9273d-112">4.7.1</span></span>|
|<span data-ttu-id="9273d-113">Type</span><span class="sxs-lookup"><span data-stu-id="9273d-113">Type</span></span>|<span data-ttu-id="9273d-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="9273d-114">Runtime</span></span>|
