---
ms.openlocfilehash: 0e949cbdeda99dd7b94e919b903a21171a57f527
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614729"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a><span data-ttu-id="e7c8a-101">Привязка WCF с режимом безопасности TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="e7c8a-101">WCF binding with the TransportWithMessageCredential security mode</span></span>

#### <a name="details"></a><span data-ttu-id="e7c8a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e7c8a-102">Details</span></span>

<span data-ttu-id="e7c8a-103">Начиная с .NET Framework 4.6.1 привязку WCF, которая использует режим безопасности TransportWithMessageCredential, можно настроить для получения сообщений с неподписанными заголовками &quot;to&quot; для асимметричных ключей безопасности. По умолчанию неподписанные заголовки &quot;to&quot; будут отклоняться в .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="e7c8a-103">Beginning in the .NET Framework 4.6.1, WCF binding that uses the TransportWithMessageCredential security mode can be set up to receive messages with unsigned &quot;to&quot; headers for asymmetric security keys.By default, unsigned &quot;to&quot; headers will continue to be rejected in .NET Framework 4.6.1.</span></span> <span data-ttu-id="e7c8a-104">Они будут приниматься только в случае перевода приложения на новый режим с помощью переключателя конфигурации Switch.System.ServiceModel.AllowUnsignedToHeader.</span><span class="sxs-lookup"><span data-stu-id="e7c8a-104">They will only be accepted if an application opts into this new mode of operation using the Switch.System.ServiceModel.AllowUnsignedToHeader configuration switch.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e7c8a-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="e7c8a-105">Suggestion</span></span>

<span data-ttu-id="e7c8a-106">Поскольку это возможность, включаемая пользователем, она не должна влиять на поведение существующих приложений.</span><span class="sxs-lookup"><span data-stu-id="e7c8a-106">Because this is an opt-in feature, it should not affect the behavior of existing apps.</span></span><br/><span data-ttu-id="e7c8a-107">Для включения или отключения нового поведения используйте следующий параметр конфигурации:</span><span class="sxs-lookup"><span data-stu-id="e7c8a-107">To control whether the new behavior is used or not, use the following configuration setting:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />
</runtime>
```

| <span data-ttu-id="e7c8a-108">name</span><span class="sxs-lookup"><span data-stu-id="e7c8a-108">Name</span></span>    | <span data-ttu-id="e7c8a-109">Значение</span><span class="sxs-lookup"><span data-stu-id="e7c8a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e7c8a-110">Область</span><span class="sxs-lookup"><span data-stu-id="e7c8a-110">Scope</span></span>   | <span data-ttu-id="e7c8a-111">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="e7c8a-111">Transparent</span></span> |
| <span data-ttu-id="e7c8a-112">Version</span><span class="sxs-lookup"><span data-stu-id="e7c8a-112">Version</span></span> | <span data-ttu-id="e7c8a-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e7c8a-113">4.6.1</span></span>       |
| <span data-ttu-id="e7c8a-114">Type</span><span class="sxs-lookup"><span data-stu-id="e7c8a-114">Type</span></span>    | <span data-ttu-id="e7c8a-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="e7c8a-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e7c8a-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e7c8a-116">Affected APIs</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
