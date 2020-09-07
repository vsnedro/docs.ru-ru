---
ms.openlocfilehash: 68b0c4bb032b9744ef585eaef3d68e31afebee24
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496139"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="8701c-101">Свойство CheckForOverflowUnderflow WinForm теперь имеет значение true для System.Drawing</span><span class="sxs-lookup"><span data-stu-id="8701c-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="8701c-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="8701c-102">Details</span></span>

<span data-ttu-id="8701c-103">Свойство CheckForOverflowUnderflow для сборки System.Drawing.dll имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="8701c-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8701c-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="8701c-104">Suggestion</span></span>

<span data-ttu-id="8701c-105">Раньше при переполнениях результат усекался без уведомления.</span><span class="sxs-lookup"><span data-stu-id="8701c-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="8701c-106">Теперь создается исключение <xref:System.OverflowException?displayProperty=fullName>,</span><span class="sxs-lookup"><span data-stu-id="8701c-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="8701c-107">name</span><span class="sxs-lookup"><span data-stu-id="8701c-107">Name</span></span>    | <span data-ttu-id="8701c-108">Значение</span><span class="sxs-lookup"><span data-stu-id="8701c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8701c-109">Область</span><span class="sxs-lookup"><span data-stu-id="8701c-109">Scope</span></span>   |<span data-ttu-id="8701c-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="8701c-110">Edge</span></span>|
|<span data-ttu-id="8701c-111">Version</span><span class="sxs-lookup"><span data-stu-id="8701c-111">Version</span></span>|<span data-ttu-id="8701c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="8701c-112">4.5</span></span>|
|<span data-ttu-id="8701c-113">Type</span><span class="sxs-lookup"><span data-stu-id="8701c-113">Type</span></span>|<span data-ttu-id="8701c-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="8701c-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8701c-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="8701c-115">Affected APIs</span></span>

<span data-ttu-id="8701c-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="8701c-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
