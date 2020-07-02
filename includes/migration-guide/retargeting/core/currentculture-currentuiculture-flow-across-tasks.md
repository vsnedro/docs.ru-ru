---
ms.openlocfilehash: 78faa5f4008b41bac75c94ce09a58c8227e5b485
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614669"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a><span data-ttu-id="91084-101">Поток CurrentCulture и CurrentUICulture между задачами</span><span class="sxs-lookup"><span data-stu-id="91084-101">CurrentCulture and CurrentUICulture flow across tasks</span></span>

#### <a name="details"></a><span data-ttu-id="91084-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="91084-102">Details</span></span>

<span data-ttu-id="91084-103">Начиная с .NET Framework 4.6 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> хранятся в <xref:System.Threading.ExecutionContext?displayProperty=fullName> потока, который проходит через асинхронные операции. Это означает, что изменения <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> будут отражены в задачах, которые позже выполняются асинхронно.</span><span class="sxs-lookup"><span data-stu-id="91084-103">Beginning in the .NET Framework 4.6, <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> are stored in the thread's <xref:System.Threading.ExecutionContext?displayProperty=fullName>, which flows across asynchronous operations.This means that changes to <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> will be reflected in tasks which are later run asynchronously.</span></span> <span data-ttu-id="91084-104">Это отличается от поведения предыдущих версий .NET Framework (которые во всех асинхронных задачах сбрасывали <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="91084-104">This is different from the behavior of previous .NET Framework versions (which would reset <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> in all asynchronous tasks).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="91084-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="91084-105">Suggestion</span></span>

<span data-ttu-id="91084-106">Приложения, которых коснулось это изменение, могут обойти его, явно задав <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> в качестве первой операции в асинхронной задаче.</span><span class="sxs-lookup"><span data-stu-id="91084-106">Apps affected by this change may work around it by explicitly setting the desired <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> as the first operation in an async Task.</span></span> <span data-ttu-id="91084-107">Кроме того, можно выбрать прежнее поведение (без потока <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) путем установки следующего переключателя совместимости:</span><span class="sxs-lookup"><span data-stu-id="91084-107">Alternatively, the old behavior (of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) may be opted into by setting the following compatibility switch:</span></span>

```csharp
AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);
```

<span data-ttu-id="91084-108">Эта проблема была устранена с помощью WPF в .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="91084-108">This issue has been fixed by WPF in .NET Framework 4.6.2.</span></span> <span data-ttu-id="91084-109">Она также была устранена в .NET Framework версий 4.6 и 4.6.1 посредством [KB 3139549](https://support.microsoft.com/kb/3139549).</span><span class="sxs-lookup"><span data-stu-id="91084-109">It has also been fixed in .NET Frameworks 4.6, 4.6.1 through [KB 3139549](https://support.microsoft.com/kb/3139549).</span></span> <span data-ttu-id="91084-110">Приложения, предназначенные для .NET Framework 4.6 или более поздней версии, автоматически получают правильное поведение в приложениях WPF — <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) будет сохранено в операциях диспетчера.</span><span class="sxs-lookup"><span data-stu-id="91084-110">Applications targeting .NET Framework 4.6 or later will automatically get the right behavior in WPF applications - <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) would be preserved across Dispatcher operations.</span></span>

| <span data-ttu-id="91084-111">name</span><span class="sxs-lookup"><span data-stu-id="91084-111">Name</span></span>    | <span data-ttu-id="91084-112">Значение</span><span class="sxs-lookup"><span data-stu-id="91084-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="91084-113">Область</span><span class="sxs-lookup"><span data-stu-id="91084-113">Scope</span></span>   | <span data-ttu-id="91084-114">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="91084-114">Minor</span></span>       |
| <span data-ttu-id="91084-115">Version</span><span class="sxs-lookup"><span data-stu-id="91084-115">Version</span></span> | <span data-ttu-id="91084-116">4.6</span><span class="sxs-lookup"><span data-stu-id="91084-116">4.6</span></span>         |
| <span data-ttu-id="91084-117">Type</span><span class="sxs-lookup"><span data-stu-id="91084-117">Type</span></span>    | <span data-ttu-id="91084-118">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="91084-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="91084-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="91084-119">Affected APIs</span></span>

- <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType>
