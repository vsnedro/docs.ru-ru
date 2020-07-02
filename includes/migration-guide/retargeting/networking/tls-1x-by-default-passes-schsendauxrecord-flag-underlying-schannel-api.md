---
ms.openlocfilehash: e7f690030a5cb5605645f1ca42a6f08dcdd214f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615766"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a><span data-ttu-id="f403d-101">TLS 1.x по умолчанию передает флаг SCH_SEND_AUX_RECORD базовому API SCHANNEL</span><span class="sxs-lookup"><span data-stu-id="f403d-101">TLS 1.x by default passes the SCH_SEND_AUX_RECORD flag to the underlying SCHANNEL API</span></span>

#### <a name="details"></a><span data-ttu-id="f403d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f403d-102">Details</span></span>

<span data-ttu-id="f403d-103">При использовании TLS 1.x .NET Framework зависит от базового интерфейса API Windows SCHANNEL.</span><span class="sxs-lookup"><span data-stu-id="f403d-103">When using TLS 1.x, the .NET Framework relies on the underlying Windows SCHANNEL API.</span></span> <span data-ttu-id="f403d-104">Начиная с .NET Framework 4.6 флаг [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) передается SCHANNEL по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f403d-104">Starting with .NET Framework 4.6, the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) flag is passed by default to SCHANNEL.</span></span> <span data-ttu-id="f403d-105">В результате SCHANNEL разбивает данные для шифрования на две отдельных записи. В первой — один байт, а во второй — <em>n</em>–1 байт. В редких случаях это нарушает логику взаимодействия между клиентами и существующими серверами, которая предполагает, что данные находятся в одной записи.</span><span class="sxs-lookup"><span data-stu-id="f403d-105">This causes SCHANNEL to split data to be encrypted into two separate records, the first as a single byte and the second as <em>n</em>-1 bytes.In rare cases, this breaks communication between clients and existing servers that make the assumption that the data resides in a single record.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f403d-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="f403d-106">Suggestion</span></span>

<span data-ttu-id="f403d-107">Если это изменение нарушает связь с существующим сервером, вы можете отключить отправку флага [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) и восстановить предыдущее поведение, при котором данные не разделяются на две записи, добавив следующий переключатель в элемент [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="f403d-107">If this change breaks communication with an existing server, you can disable sending the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) flag and restore the previous behavior of not splitting data into separate records by adding the following switch to the [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchSendAuxRecord=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="f403d-108">Этот параметр предоставляется исключительно для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="f403d-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="f403d-109">Его использование в других целях не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="f403d-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="f403d-110">name</span><span class="sxs-lookup"><span data-stu-id="f403d-110">Name</span></span>    | <span data-ttu-id="f403d-111">Значение</span><span class="sxs-lookup"><span data-stu-id="f403d-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f403d-112">Область</span><span class="sxs-lookup"><span data-stu-id="f403d-112">Scope</span></span>   | <span data-ttu-id="f403d-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="f403d-113">Edge</span></span>        |
| <span data-ttu-id="f403d-114">Version</span><span class="sxs-lookup"><span data-stu-id="f403d-114">Version</span></span> | <span data-ttu-id="f403d-115">4.6</span><span class="sxs-lookup"><span data-stu-id="f403d-115">4.6</span></span>         |
| <span data-ttu-id="f403d-116">Type</span><span class="sxs-lookup"><span data-stu-id="f403d-116">Type</span></span>    | <span data-ttu-id="f403d-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="f403d-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="f403d-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f403d-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
