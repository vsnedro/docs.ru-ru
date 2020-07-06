---
ms.openlocfilehash: d3e0a61601f60a389b662f6f74934b6e6dc6e663
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614916"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a><span data-ttu-id="1812c-101">В качестве хэш-алгоритма по умолчанию для PackageDigitalSignatureManager WPF теперь используется SHA256</span><span class="sxs-lookup"><span data-stu-id="1812c-101">The default hash algorithm for WPF PackageDigitalSignatureManager is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="1812c-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="1812c-102">Details</span></span>

<span data-ttu-id="1812c-103">`System.IO.Packaging.PackageDigitalSignatureManager` реализует функции цифровой подписи для пакетов WPF.</span><span class="sxs-lookup"><span data-stu-id="1812c-103">The `System.IO.Packaging.PackageDigitalSignatureManager` provides functionality for digital signatures in relation to WPF packages.</span></span>  <span data-ttu-id="1812c-104">В .NET Framework 4.7 и более ранних версиях для подписывания частей пакетов по умолчанию использовался хэш-алгоритм SHA1 (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="1812c-104">In the .NET Framework 4.7 and earlier versions, the default algorithm (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) used for signing parts of a package was SHA1.</span></span>  <span data-ttu-id="1812c-105">С учетом выявленных проблем с безопасностью SHA1, начиная с версии .NET Framework 4.7.1, теперь по умолчанию используется алгоритм SHA256.</span><span class="sxs-lookup"><span data-stu-id="1812c-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.1.</span></span>  <span data-ttu-id="1812c-106">Это изменение затрагивает все операции подписывания пакетов, включая документы XPS.</span><span class="sxs-lookup"><span data-stu-id="1812c-106">This change affects all package signing, including XPS documents.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1812c-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="1812c-107">Suggestion</span></span>

<span data-ttu-id="1812c-108">Тем разработчикам, которые хотят реализовать это изменение в приложениях для версий платформы .NET Framework ниже 4.7.1, а также тем, кому необходимо использовать старые функции в приложениях для версии .NET Framework 4.7.1 или более поздних, необходимо соответствующим образом установить флаг AppContext.</span><span class="sxs-lookup"><span data-stu-id="1812c-108">A developer who wants to utilize this change while targeting a framework version below .NET Framework 4.7.1 or a developer who requires the previous functionality while targeting .NET Framework 4.7.1 or greater can set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="1812c-109">Чтобы использовать алгоритм SHA1, следует установить значение true. Значение false позволяет использовать алгоритм SHA256.</span><span class="sxs-lookup"><span data-stu-id="1812c-109">A value of true will result in SHA1 being used as the default algorithm; false results in SHA256.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="1812c-110">name</span><span class="sxs-lookup"><span data-stu-id="1812c-110">Name</span></span>    | <span data-ttu-id="1812c-111">Значение</span><span class="sxs-lookup"><span data-stu-id="1812c-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1812c-112">Область</span><span class="sxs-lookup"><span data-stu-id="1812c-112">Scope</span></span>   | <span data-ttu-id="1812c-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="1812c-113">Edge</span></span>        |
| <span data-ttu-id="1812c-114">Version</span><span class="sxs-lookup"><span data-stu-id="1812c-114">Version</span></span> | <span data-ttu-id="1812c-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="1812c-115">4.7.1</span></span>       |
| <span data-ttu-id="1812c-116">Type</span><span class="sxs-lookup"><span data-stu-id="1812c-116">Type</span></span>    | <span data-ttu-id="1812c-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="1812c-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1812c-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="1812c-118">Affected APIs</span></span>

- <xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>
