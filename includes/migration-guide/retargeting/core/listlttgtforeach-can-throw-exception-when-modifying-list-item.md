---
ms.openlocfilehash: 3300a74b81fc9eeba670ee0ceb2c2615fd3925bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617284"
---
### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="087bc-101">List&lt;T&gt;.ForEach может создавать исключение при изменении элемента списка</span><span class="sxs-lookup"><span data-stu-id="087bc-101">List&lt;T&gt;.ForEach can throw exception when modifying list item</span></span>

#### <a name="details"></a><span data-ttu-id="087bc-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="087bc-102">Details</span></span>

<span data-ttu-id="087bc-103">Начиная с .NET Framework 4.5 перечислитель <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> будет создавать исключение <xref:System.InvalidOperationException?displayProperty=fullName> при изменении элемента в вызывающей коллекции.</span><span class="sxs-lookup"><span data-stu-id="087bc-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=fullName> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="087bc-104">Ранее исключение не создавалось, но могли возникать конфликты.</span><span class="sxs-lookup"><span data-stu-id="087bc-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="087bc-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="087bc-105">Suggestion</span></span>

<span data-ttu-id="087bc-106">В идеальном случае следует исправить код, чтобы он не изменял списки при перечислении их элементов, поскольку эта операция небезопасна.</span><span class="sxs-lookup"><span data-stu-id="087bc-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="087bc-107">Чтобы вернуться к предыдущему поведению, приложение должно быть предназначено для платформы .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="087bc-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>

| <span data-ttu-id="087bc-108">name</span><span class="sxs-lookup"><span data-stu-id="087bc-108">Name</span></span>    | <span data-ttu-id="087bc-109">Значение</span><span class="sxs-lookup"><span data-stu-id="087bc-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="087bc-110">Область</span><span class="sxs-lookup"><span data-stu-id="087bc-110">Scope</span></span>   | <span data-ttu-id="087bc-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="087bc-111">Edge</span></span>        |
| <span data-ttu-id="087bc-112">Version</span><span class="sxs-lookup"><span data-stu-id="087bc-112">Version</span></span> | <span data-ttu-id="087bc-113">4.5</span><span class="sxs-lookup"><span data-stu-id="087bc-113">4.5</span></span>         |
| <span data-ttu-id="087bc-114">Type</span><span class="sxs-lookup"><span data-stu-id="087bc-114">Type</span></span>    | <span data-ttu-id="087bc-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="087bc-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="087bc-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="087bc-116">Affected APIs</span></span>

- <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType>
