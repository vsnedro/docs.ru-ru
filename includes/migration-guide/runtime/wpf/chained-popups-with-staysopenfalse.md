---
ms.openlocfilehash: 171b7a3a962f8259e64b88f1ae893e649b5f24bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621252"
---
### <a name="chained-popups-with-staysopenfalse"></a><span data-ttu-id="14b61-101">Связанные всплывающие окна с StaysOpen=False</span><span class="sxs-lookup"><span data-stu-id="14b61-101">Chained Popups with StaysOpen=False</span></span>

#### <a name="details"></a><span data-ttu-id="14b61-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="14b61-102">Details</span></span>

<span data-ttu-id="14b61-103">Всплывающее окно с StaysOpen=False должно закрываться при щелчке за пределами всплывающего окна.</span><span class="sxs-lookup"><span data-stu-id="14b61-103">A Popup with StaysOpen=False is supposed to close when you click outside the Popup.</span></span> <span data-ttu-id="14b61-104">Если несколько таких всплывающих окон связаны по цепочке (например, одно содержит другое), возникает множество проблем, в том числе следующие:</span><span class="sxs-lookup"><span data-stu-id="14b61-104">When two or more such Popups are chained (i.e. one contains another), there were many problems, including:</span></span><ul><li><span data-ttu-id="14b61-105">Откройте два уровня и щелкните вне окна P2, но внутри окна P1.</span><span class="sxs-lookup"><span data-stu-id="14b61-105">Open two levels, click outside P2 but inside P1.</span></span>  <span data-ttu-id="14b61-106">Ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="14b61-106">Nothing happens.</span></span></li><li><span data-ttu-id="14b61-107">Откройте два уровня и щелкните вне окна P1.</span><span class="sxs-lookup"><span data-stu-id="14b61-107">Open two levels, click outside P1.</span></span>  <span data-ttu-id="14b61-108">Оба всплывающих окна закроются.</span><span class="sxs-lookup"><span data-stu-id="14b61-108">Both popups close.</span></span></li><li><span data-ttu-id="14b61-109">Откройте и закройте два уровня.</span><span class="sxs-lookup"><span data-stu-id="14b61-109">Open and close two levels.</span></span>  <span data-ttu-id="14b61-110">Теперь попытайтесь снова открыть окно P2.</span><span class="sxs-lookup"><span data-stu-id="14b61-110">Then try to open P2 again.</span></span>  <span data-ttu-id="14b61-111">Ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="14b61-111">Nothing happens.</span></span></li><li><span data-ttu-id="14b61-112">Попробуйте открыть три уровня.</span><span class="sxs-lookup"><span data-stu-id="14b61-112">Try to open three levels.</span></span>  <span data-ttu-id="14b61-113">Это невозможно.</span><span class="sxs-lookup"><span data-stu-id="14b61-113">You can't.</span></span>  <span data-ttu-id="14b61-114">(В зависимости от места щелчка, либо ничего не происходит, либо первые два уровня закрываются.) Теперь поведение окон в этих и других случаях исправлено.</span><span class="sxs-lookup"><span data-stu-id="14b61-114">(Either nothing happens or the first two levels close, depending on where you click.) These cases (and other variants) now work as expected.</span></span></li></ul>

| <span data-ttu-id="14b61-115">name</span><span class="sxs-lookup"><span data-stu-id="14b61-115">Name</span></span>    | <span data-ttu-id="14b61-116">Значение</span><span class="sxs-lookup"><span data-stu-id="14b61-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="14b61-117">Область</span><span class="sxs-lookup"><span data-stu-id="14b61-117">Scope</span></span>   |<span data-ttu-id="14b61-118">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="14b61-118">Edge</span></span>|
|<span data-ttu-id="14b61-119">Version</span><span class="sxs-lookup"><span data-stu-id="14b61-119">Version</span></span>|<span data-ttu-id="14b61-120">4.7.1</span><span class="sxs-lookup"><span data-stu-id="14b61-120">4.7.1</span></span>|
|<span data-ttu-id="14b61-121">Type</span><span class="sxs-lookup"><span data-stu-id="14b61-121">Type</span></span>|<span data-ttu-id="14b61-122">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="14b61-122">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="14b61-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="14b61-123">Affected APIs</span></span>

-<xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|
