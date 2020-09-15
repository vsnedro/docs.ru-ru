---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614811"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a><span data-ttu-id="78c57-101">Алгоритмы SignedXML и SignedXMS по умолчанию изменены на SHA256</span><span class="sxs-lookup"><span data-stu-id="78c57-101">Default SignedXML and SignedXMS algorithms changed to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="78c57-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="78c57-102">Details</span></span>

<span data-ttu-id="78c57-103">В .NET Framework 4.7 и более ранних версий SignedXML и SignedCMS по умолчанию изменены на SHA-1 для некоторых операций. Начиная с .NET Framework 4.7.1 по умолчанию для этих операций включен SHA256.</span><span class="sxs-lookup"><span data-stu-id="78c57-103">In the .NET Framework 4.7 and earlier, SignedXML and SignedCMS default to SHA1 for some operations.Starting with the .NET Framework 4.7.1, SHA256 is enabled by default for these operations.</span></span> <span data-ttu-id="78c57-104">Это изменение было необходимо, поскольку алгоритм SHA-1 больше не считается безопасным.</span><span class="sxs-lookup"><span data-stu-id="78c57-104">This change is necessary because SHA1 is no longer considered to be secure.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="78c57-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="78c57-105">Suggestion</span></span>

<span data-ttu-id="78c57-106">Существует два новых значения переключения контекста для выбора алгоритма SHA-1 (небезопасно) или SHA256 по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="78c57-106">There are two new context switch values to control whether SHA1 (insecure) or SHA256 is used by default:</span></span>

- <span data-ttu-id="78c57-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span><span class="sxs-lookup"><span data-stu-id="78c57-107">Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</span></span>
- <span data-ttu-id="78c57-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms Если в приложениях, предназначенных для .NET Framework 4.7.1 и более поздних версий, использовать SHA256 нежелательно, можно изменить алгоритм по умолчанию на SHA1, добавив следующую конфигурацию в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="78c57-108">Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms For applications that target the .NET Framework 4.7.1 and later versions, if the use of SHA256 is undesirable, you can restore the default to SHA1 by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

<span data-ttu-id="78c57-109">В приложениях, предназначенных для .NET Framework 4.7 и более ранних версий, вы можете выбрать это изменение, добавив следующую конфигурацию в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="78c57-109">For applications that target the .NET Framework 4.7 and earlier versions, you can opt into this change by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| <span data-ttu-id="78c57-110">name</span><span class="sxs-lookup"><span data-stu-id="78c57-110">Name</span></span>    | <span data-ttu-id="78c57-111">Значение</span><span class="sxs-lookup"><span data-stu-id="78c57-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="78c57-112">Область</span><span class="sxs-lookup"><span data-stu-id="78c57-112">Scope</span></span>   | <span data-ttu-id="78c57-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="78c57-113">Minor</span></span>       |
| <span data-ttu-id="78c57-114">Версия</span><span class="sxs-lookup"><span data-stu-id="78c57-114">Version</span></span> | <span data-ttu-id="78c57-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="78c57-115">4.7.1</span></span>       |
| <span data-ttu-id="78c57-116">Type</span><span class="sxs-lookup"><span data-stu-id="78c57-116">Type</span></span>    | <span data-ttu-id="78c57-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="78c57-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="78c57-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="78c57-118">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>
