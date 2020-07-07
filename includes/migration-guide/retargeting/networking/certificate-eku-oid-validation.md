---
ms.openlocfilehash: c996dafcf65b1fd428be908be346de603ead6e0b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615755"
---
### <a name="certificate-eku-oid-validation"></a><span data-ttu-id="00aaa-101">Проверка OID EKU сертификата</span><span class="sxs-lookup"><span data-stu-id="00aaa-101">Certificate EKU OID validation</span></span>

#### <a name="details"></a><span data-ttu-id="00aaa-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="00aaa-102">Details</span></span>

<span data-ttu-id="00aaa-103">Начиная с .NET Framework 4.6 классы <xref:System.Net.Security.SslStream> или <xref:System.Net.ServicePointManager> выполняют проверку идентификатора объекта (OID) расширенного использования ключа (EKU).</span><span class="sxs-lookup"><span data-stu-id="00aaa-103">Starting with .NET Framework 4.6, the <xref:System.Net.Security.SslStream> or <xref:System.Net.ServicePointManager> classes perform enhanced key use (EKU) object identifier (OID) validation.</span></span> <span data-ttu-id="00aaa-104">Расширение расширенного использования ключа (EKU) — это коллекция идентификаторов объекта (OID), которые указывают приложения, использующие ключ.</span><span class="sxs-lookup"><span data-stu-id="00aaa-104">An enhanced key usage (EKU) extension is a collection of object identifiers (OIDs) that indicate the applications that use the key.</span></span> <span data-ttu-id="00aaa-105">При проверке OID EKU используются обратные вызовы удаленного сертификата, чтобы у удаленного сертификата были правильные OID для указанных целей.</span><span class="sxs-lookup"><span data-stu-id="00aaa-105">EKU OID validation uses remote certificate callbacks to ensure that the remote certificate has the correct OIDs for the intended purpose.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="00aaa-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="00aaa-106">Suggestion</span></span>

<span data-ttu-id="00aaa-107">Если это изменение нежелательно, можно отключить проверку OID EKU сертификата, добавив следующий параметр к [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) в файле конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="00aaa-107">If this change is undesirable, you can disable certificate EKU OID validation by adding the following switch to the [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontCheckCertificateEKUs=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="00aaa-108">Этот параметр предоставляется исключительно для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="00aaa-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="00aaa-109">Его использование в других целях не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="00aaa-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="00aaa-110">name</span><span class="sxs-lookup"><span data-stu-id="00aaa-110">Name</span></span>    | <span data-ttu-id="00aaa-111">Значение</span><span class="sxs-lookup"><span data-stu-id="00aaa-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="00aaa-112">Область</span><span class="sxs-lookup"><span data-stu-id="00aaa-112">Scope</span></span>   | <span data-ttu-id="00aaa-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="00aaa-113">Minor</span></span>       |
| <span data-ttu-id="00aaa-114">Version</span><span class="sxs-lookup"><span data-stu-id="00aaa-114">Version</span></span> | <span data-ttu-id="00aaa-115">4.6</span><span class="sxs-lookup"><span data-stu-id="00aaa-115">4.6</span></span>         |
| <span data-ttu-id="00aaa-116">Type</span><span class="sxs-lookup"><span data-stu-id="00aaa-116">Type</span></span>    | <span data-ttu-id="00aaa-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="00aaa-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="00aaa-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="00aaa-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
