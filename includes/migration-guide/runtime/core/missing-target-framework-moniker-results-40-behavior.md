---
ms.openlocfilehash: 49740d3b1890d72935e6e329a4f4be836ed70b25
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496375"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a><span data-ttu-id="5dcdf-101">Отсутствие моникера целевой платформы приводит к поведению версии 4.0</span><span class="sxs-lookup"><span data-stu-id="5dcdf-101">Missing Target Framework Moniker results in 4.0 behavior</span></span>

#### <a name="details"></a><span data-ttu-id="5dcdf-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5dcdf-102">Details</span></span>

<span data-ttu-id="5dcdf-103">Приложения без атрибута <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>, примененного на уровне сборки, будут автоматически запускаться с использованием семантики (особенностей) платформы .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="5dcdf-103">Applications without a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> applied at the assembly level will automatically run using the semantics (quirks) of the .NET Framework 4.0.</span></span> <span data-ttu-id="5dcdf-104">Для обеспечения высокого качества рекомендуется явным образом применить ко всем двоичным файлам атрибут <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>, указывающий версию платформы .NET Framework, в которой они были созданы.</span><span class="sxs-lookup"><span data-stu-id="5dcdf-104">To ensure high quality, it is recommended that all binaries be explicitly attributed with a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> indicating the version of the .NET Framework they were built with.</span></span> <span data-ttu-id="5dcdf-105">Обратите внимание, что при использовании моникера целевой платформы в файле проекта MSBuild будет автоматически применять <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5dcdf-105">Note that using a target framework moniker in a project file will cause MSBuild to automatically apply a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5dcdf-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="5dcdf-106">Suggestion</span></span>

<span data-ttu-id="5dcdf-107">Атрибут <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> должен быть предоставлен либо путем его добавления непосредственно в сборку, либо путем указания целевой платформы в [файле проекта или с помощью графического интерфейса свойств проекта Visual Studio](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span><span class="sxs-lookup"><span data-stu-id="5dcdf-107">A <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> should be supplied, either through adding the attribute directly to the assembly or by specifying a target framework in the [project file or through Visual Studio's project properties GUI](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span></span>

| <span data-ttu-id="5dcdf-108">name</span><span class="sxs-lookup"><span data-stu-id="5dcdf-108">Name</span></span>    | <span data-ttu-id="5dcdf-109">Значение</span><span class="sxs-lookup"><span data-stu-id="5dcdf-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5dcdf-110">Область</span><span class="sxs-lookup"><span data-stu-id="5dcdf-110">Scope</span></span>   |<span data-ttu-id="5dcdf-111">Значительно</span><span class="sxs-lookup"><span data-stu-id="5dcdf-111">Major</span></span>|
|<span data-ttu-id="5dcdf-112">Version</span><span class="sxs-lookup"><span data-stu-id="5dcdf-112">Version</span></span>|<span data-ttu-id="5dcdf-113">4.5</span><span class="sxs-lookup"><span data-stu-id="5dcdf-113">4.5</span></span>|
|<span data-ttu-id="5dcdf-114">Type</span><span class="sxs-lookup"><span data-stu-id="5dcdf-114">Type</span></span>|<span data-ttu-id="5dcdf-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="5dcdf-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="5dcdf-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="5dcdf-116">Affected APIs</span></span>

<span data-ttu-id="5dcdf-117">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="5dcdf-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
