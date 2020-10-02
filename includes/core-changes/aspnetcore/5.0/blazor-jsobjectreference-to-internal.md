---
ms.openlocfilehash: 46f6f77a543dfcf2073063d8ec200ef7d71e6b1f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077596"
---
### <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a><span data-ttu-id="cfcf4-101">Blazor: Типы JSObjectReference и JSInProcessObjectReference изменены на internal</span><span class="sxs-lookup"><span data-stu-id="cfcf4-101">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>

<span data-ttu-id="cfcf4-102">Новые типы `Microsoft.JSInterop.JSObjectReference` и `Microsoft.JSInterop.JSInProcessObjectReference`, появившиеся в ASP.NET Core 5.0 RC1, помечены как `internal`.</span><span class="sxs-lookup"><span data-stu-id="cfcf4-102">The new `Microsoft.JSInterop.JSObjectReference` and `Microsoft.JSInterop.JSInProcessObjectReference` types introduced in ASP.NET Core 5.0 RC1 have been marked as `internal`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cfcf4-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="cfcf4-103">Version introduced</span></span>

<span data-ttu-id="cfcf4-104">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="cfcf4-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cfcf4-105">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="cfcf4-105">Old behavior</span></span>

<span data-ttu-id="cfcf4-106">`JSObjectReference` можно получить из вызова взаимодействия JavaScript через `IJSRuntime`.</span><span class="sxs-lookup"><span data-stu-id="cfcf4-106">A `JSObjectReference` can be obtained from a JavaScript interop call via `IJSRuntime`.</span></span> <span data-ttu-id="cfcf4-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="cfcf4-107">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

#### <a name="new-behavior"></a><span data-ttu-id="cfcf4-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="cfcf4-108">New behavior</span></span>

<span data-ttu-id="cfcf4-109">`JSObjectReference` использует модификатор доступа [internal](../../../../docs/csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="cfcf4-109">`JSObjectReference` uses the [internal](../../../../docs/csharp/language-reference/keywords/internal.md) access modifier.</span></span> <span data-ttu-id="cfcf4-110">Вместо этого необходимо использовать интерфейс `public` `IJSObjectReference`.</span><span class="sxs-lookup"><span data-stu-id="cfcf4-110">The `public` `IJSObjectReference` interface must be used instead.</span></span> <span data-ttu-id="cfcf4-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="cfcf4-111">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

<span data-ttu-id="cfcf4-112">`JSInProcessObjectReference` также помечен как `internal` и изменен на `IJSInProcessObjectReference`.</span><span class="sxs-lookup"><span data-stu-id="cfcf4-112">`JSInProcessObjectReference` was also marked as `internal` and was replaced by `IJSInProcessObjectReference`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cfcf4-113">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="cfcf4-113">Reason for change</span></span>

<span data-ttu-id="cfcf4-114">Это изменение делает функцию взаимодействия JavaScript более совместимой с другими шаблонами в Blazor.</span><span class="sxs-lookup"><span data-stu-id="cfcf4-114">The change makes the JavaScript interop feature more consistent with other patterns within Blazor.</span></span> <span data-ttu-id="cfcf4-115">`IJSObjectReference` можно использовать как `IJSRuntime` в контексте назначения и методов и расширения.</span><span class="sxs-lookup"><span data-stu-id="cfcf4-115">`IJSObjectReference` is analogous to `IJSRuntime` in that it serves a similar purpose and has similar methods and extensions.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cfcf4-116">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="cfcf4-116">Recommended action</span></span>

<span data-ttu-id="cfcf4-117">Измените вхождения `JSObjectReference` и `JSInProcessObjectReference` на `IJSObjectReference` и `IJSInProcessObjectReference`соответственно.</span><span class="sxs-lookup"><span data-stu-id="cfcf4-117">Replace occurrences of `JSObjectReference` and `JSInProcessObjectReference` with `IJSObjectReference` and `IJSInProcessObjectReference`, respectively.</span></span>

#### <a name="category"></a><span data-ttu-id="cfcf4-118">Категория</span><span class="sxs-lookup"><span data-stu-id="cfcf4-118">Category</span></span>

<span data-ttu-id="cfcf4-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cfcf4-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cfcf4-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="cfcf4-120">Affected APIs</span></span>

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

#### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
