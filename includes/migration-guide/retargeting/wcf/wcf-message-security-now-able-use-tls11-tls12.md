---
ms.openlocfilehash: c646372104457e8bc5d418744847f3ee771c8d8b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614804"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="1f418-101">Для безопасности сообщений WCF теперь могут использоваться TLS1.1 и TLS1.2</span><span class="sxs-lookup"><span data-stu-id="1f418-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

#### <a name="details"></a><span data-ttu-id="1f418-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="1f418-102">Details</span></span>

<span data-ttu-id="1f418-103">Начиная с .NET Framework 4.7 клиенты могут настроить в параметрах конфигурации приложения не только SSL3.0 и TLS1.0, но и TLS1.1 или TLS1.2.</span><span class="sxs-lookup"><span data-stu-id="1f418-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1f418-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="1f418-104">Suggestion</span></span>

<span data-ttu-id="1f418-105">В .NET Framework 4.7 поддержка TLS1.1 и TLS1.2 в безопасности сообщений WCF по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="1f418-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="1f418-106">Вы можете включить ее, добавив следующую строку в раздел `<runtime>` файла app.config или web.config:</span><span class="sxs-lookup"><span data-stu-id="1f418-106">You can enable it by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

| <span data-ttu-id="1f418-107">name</span><span class="sxs-lookup"><span data-stu-id="1f418-107">Name</span></span>    | <span data-ttu-id="1f418-108">Значение</span><span class="sxs-lookup"><span data-stu-id="1f418-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1f418-109">Область</span><span class="sxs-lookup"><span data-stu-id="1f418-109">Scope</span></span>   | <span data-ttu-id="1f418-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="1f418-110">Edge</span></span>        |
| <span data-ttu-id="1f418-111">Version</span><span class="sxs-lookup"><span data-stu-id="1f418-111">Version</span></span> | <span data-ttu-id="1f418-112">4.7</span><span class="sxs-lookup"><span data-stu-id="1f418-112">4.7</span></span>         |
| <span data-ttu-id="1f418-113">Type</span><span class="sxs-lookup"><span data-stu-id="1f418-113">Type</span></span>    | <span data-ttu-id="1f418-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="1f418-114">Retargeting</span></span> |
