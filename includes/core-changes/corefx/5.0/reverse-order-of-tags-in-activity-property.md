---
ms.openlocfilehash: 24b88b3ba1b6cfe9fb9fb1f6398a6daeb57596a9
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756118"
---
### <a name="order-of-tags-in-activitytags-is-reversed"></a><span data-ttu-id="14928-101">Порядок тегов в действии Activity.Tags обращен</span><span class="sxs-lookup"><span data-stu-id="14928-101">Order of tags in Activity.Tags is reversed</span></span>

<span data-ttu-id="14928-102"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> теперь сохраняет элементы в списке в соответствии с порядком их добавления, то есть первый добавленный элемент отображается в списке первым.</span><span class="sxs-lookup"><span data-stu-id="14928-102"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> now stores items in the list according to the order they are added, that is, the first item that's added is first in the list.</span></span> <span data-ttu-id="14928-103">Это изменение было внесено в соответствии со [спецификацией атрибутов OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span><span class="sxs-lookup"><span data-stu-id="14928-103">This change was made to match the [OpenTelemetry Attributes specification](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span></span>

#### <a name="change-description"></a><span data-ttu-id="14928-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="14928-104">Change description</span></span>

<span data-ttu-id="14928-105">В предыдущих версиях .NET <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> сохраняет элементы в порядке, обратном их добавлению.</span><span class="sxs-lookup"><span data-stu-id="14928-105">In previous .NET versions, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> stores items in the reverse order from which they're added.</span></span> <span data-ttu-id="14928-106">Это значит, что первый добавленный элемент является последним в списке.</span><span class="sxs-lookup"><span data-stu-id="14928-106">That is, the first item added is last in the list.</span></span> <span data-ttu-id="14928-107">Начиная с .NET 5.0 порядок элементов теперь обратный, и первый добавленный элемент всегда находится в списке первым.</span><span class="sxs-lookup"><span data-stu-id="14928-107">Starting in .NET 5.0, the order of the items is reversed, and the first item added is always first in the list.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="14928-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="14928-108">Version introduced</span></span>

<span data-ttu-id="14928-109">5.0</span><span class="sxs-lookup"><span data-stu-id="14928-109">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="14928-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="14928-110">Recommended action</span></span>

<span data-ttu-id="14928-111">Если приложение зависит от порядка элементов в списке <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> и выполняется обновление до .NET 5.0 или более поздней версии, необходимо изменить эту часть кода.</span><span class="sxs-lookup"><span data-stu-id="14928-111">If your app has a dependency on the <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> list order and you're upgrading to .NET 5.0 or later, you'll need to change this part of your code.</span></span>

#### <a name="category"></a><span data-ttu-id="14928-112">Категория</span><span class="sxs-lookup"><span data-stu-id="14928-112">Category</span></span>

<span data-ttu-id="14928-113">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="14928-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="14928-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="14928-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
