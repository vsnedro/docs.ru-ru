---
ms.openlocfilehash: 4cd06fd02fadbaa9f74e40f850e688ee883454ed
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620696"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="ada4b-101">Свойство CheckForOverflowUnderflow WinForm теперь имеет значение true для System.Drawing</span><span class="sxs-lookup"><span data-stu-id="ada4b-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="ada4b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ada4b-102">Details</span></span>

<span data-ttu-id="ada4b-103">Свойство CheckForOverflowUnderflow для сборки System.Drawing.dll имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="ada4b-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ada4b-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="ada4b-104">Suggestion</span></span>

<span data-ttu-id="ada4b-105">Раньше при переполнениях результат усекался без уведомления.</span><span class="sxs-lookup"><span data-stu-id="ada4b-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="ada4b-106">Теперь создается исключение <xref:System.OverflowException?displayProperty=fullName>,</span><span class="sxs-lookup"><span data-stu-id="ada4b-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="ada4b-107">name</span><span class="sxs-lookup"><span data-stu-id="ada4b-107">Name</span></span>    | <span data-ttu-id="ada4b-108">Значение</span><span class="sxs-lookup"><span data-stu-id="ada4b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ada4b-109">Область</span><span class="sxs-lookup"><span data-stu-id="ada4b-109">Scope</span></span>   |<span data-ttu-id="ada4b-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="ada4b-110">Edge</span></span>|
|<span data-ttu-id="ada4b-111">Version</span><span class="sxs-lookup"><span data-stu-id="ada4b-111">Version</span></span>|<span data-ttu-id="ada4b-112">4.5</span><span class="sxs-lookup"><span data-stu-id="ada4b-112">4.5</span></span>|
|<span data-ttu-id="ada4b-113">Type</span><span class="sxs-lookup"><span data-stu-id="ada4b-113">Type</span></span>|<span data-ttu-id="ada4b-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="ada4b-114">Runtime</span></span>|
