---
ms.openlocfilehash: 80d13609f1b02ae0ac875b2028e745670bb8f503
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050574"
---
### <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a><span data-ttu-id="acff4-101">Значение FrameworkDescription изменено с .NET Core на .NET</span><span class="sxs-lookup"><span data-stu-id="acff4-101">FrameworkDescription's value is .NET instead of .NET Core</span></span>

<span data-ttu-id="acff4-102"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> теперь возвращает ".NET" вместо ".NET Core".</span><span class="sxs-lookup"><span data-stu-id="acff4-102"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> now returns ".NET" instead of ".NET Core".</span></span>

#### <a name="change-description"></a><span data-ttu-id="acff4-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="acff4-103">Change description</span></span>

<span data-ttu-id="acff4-104">В предыдущих версиях .NET <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> возвращает ".NET Core" в составе строки описания, например `.NET Core 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="acff4-104">In previous .NET versions, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET Core" as part of the description string, for example, `.NET Core 3.1.1`.</span></span>

<span data-ttu-id="acff4-105">Начиная с .NET 5.0 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> возвращает ".NET" в составе строки описания, например `.NET 5.0.0`.</span><span class="sxs-lookup"><span data-stu-id="acff4-105">Starting in .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET" as part of the description string, for example, `.NET 5.0.0`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="acff4-106">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="acff4-106">Reason for change</span></span>

<span data-ttu-id="acff4-107">В .NET 5 в качестве краткого моникера целевой платформы вместо `netcoreapp` используется `net`.</span><span class="sxs-lookup"><span data-stu-id="acff4-107">With .NET 5, `netcoreapp` is replaced by `net` as the short target-framework moniker.</span></span> <span data-ttu-id="acff4-108">В целях обеспечения согласованности также было обновлено описание платформы.</span><span class="sxs-lookup"><span data-stu-id="acff4-108">For consistency, the framework's description has also been updated.</span></span> <span data-ttu-id="acff4-109">Это изменение носит косметический характер, так как `FrameworkName` кодируется только в свойстве <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="acff4-109">The change is cosmetic, as the `FrameworkName` isn't encoded anywhere else than in the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="acff4-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="acff4-110">Version introduced</span></span>

<span data-ttu-id="acff4-111">5.0</span><span class="sxs-lookup"><span data-stu-id="acff4-111">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="acff4-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="acff4-112">Recommended action</span></span>

<span data-ttu-id="acff4-113">Обновите код, в котором выполняется поиск ".NET Core" в строке, возвращаемой <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span><span class="sxs-lookup"><span data-stu-id="acff4-113">Update any code that searches for ".NET Core" in the string returned by <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span></span>

#### <a name="category"></a><span data-ttu-id="acff4-114">Категория</span><span class="sxs-lookup"><span data-stu-id="acff4-114">Category</span></span>

<span data-ttu-id="acff4-115">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="acff4-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="acff4-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="acff4-116">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
