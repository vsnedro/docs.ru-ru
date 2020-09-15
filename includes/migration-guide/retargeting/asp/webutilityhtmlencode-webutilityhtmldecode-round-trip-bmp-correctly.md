---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617259"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a><span data-ttu-id="05d12-101">WebUtility.HtmlEncode и WebUtility.HtmlDecode корректно совершают круговой путь в BMP</span><span class="sxs-lookup"><span data-stu-id="05d12-101">WebUtility.HtmlEncode and WebUtility.HtmlDecode round-trip BMP correctly</span></span>

#### <a name="details"></a><span data-ttu-id="05d12-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="05d12-102">Details</span></span>

<span data-ttu-id="05d12-103">Для приложений, предназначенных для .NET Framework 4.5, символы, не входящие в базовый многоязыковый набор кодировок (BMP), правильно передаются в оба конца, если они передаются методам <xref:System.Net.WebUtility.HtmlDecode(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="05d12-103">For applications that target the .NET Framework 4.5, characters that are outside the Basic Multilingual Plane (BMP) round-trip correctly when they are passed to the <xref:System.Net.WebUtility.HtmlDecode(System.String)> methods.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="05d12-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="05d12-104">Suggestion</span></span>

<span data-ttu-id="05d12-105">Это изменение не должно влиять на текущие приложения, но для восстановления исходного поведения задайте атрибут `targetFramework` элемента `<httpRuntime>` для строки, отличный от "4.5".</span><span class="sxs-lookup"><span data-stu-id="05d12-105">This change should have no effect on current applications, but to restore the original behavior, set the `targetFramework` attribute of the `<httpRuntime>` element to a string other than "4.5".</span></span> <span data-ttu-id="05d12-106">Также можно задать атрибуты `unicodeEncodingConformance` и `unicodeDecodingConformance` элемента конфигурации `<webUtility>`, чтобы контролировать это поведение вне зависимости от целевой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05d12-106">You can also set the `unicodeEncodingConformance` and `unicodeDecodingConformance` attributes of the `<webUtility>` configuration element to control this behavior independently of the targeted version of the .NET Framework.</span></span>

| <span data-ttu-id="05d12-107">name</span><span class="sxs-lookup"><span data-stu-id="05d12-107">Name</span></span>    | <span data-ttu-id="05d12-108">Значение</span><span class="sxs-lookup"><span data-stu-id="05d12-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="05d12-109">Область</span><span class="sxs-lookup"><span data-stu-id="05d12-109">Scope</span></span>   | <span data-ttu-id="05d12-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="05d12-110">Edge</span></span>        |
| <span data-ttu-id="05d12-111">Version</span><span class="sxs-lookup"><span data-stu-id="05d12-111">Version</span></span> | <span data-ttu-id="05d12-112">4.5</span><span class="sxs-lookup"><span data-stu-id="05d12-112">4.5</span></span>         |
| <span data-ttu-id="05d12-113">Type</span><span class="sxs-lookup"><span data-stu-id="05d12-113">Type</span></span>    | <span data-ttu-id="05d12-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="05d12-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="05d12-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="05d12-115">Affected APIs</span></span>

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
