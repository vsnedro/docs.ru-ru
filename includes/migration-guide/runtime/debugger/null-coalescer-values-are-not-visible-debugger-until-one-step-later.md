---
ms.openlocfilehash: af8de731ee93d0bfb01042d894f5730570dcdd78
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497580"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="8ad84-101">Значения NULL операции объединения отображаются в отладчике с запаздыванием на один шаг</span><span class="sxs-lookup"><span data-stu-id="8ad84-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="8ad84-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="8ad84-102">Details</span></span>

<span data-ttu-id="8ad84-103">Из-за ошибки в .NET Framework 4.5 значения, заданные с использованием операции объединения NULL, не отображаются в отладчике немедленно после выполнения операции присваивания в 64-разрядной версии платформы.</span><span class="sxs-lookup"><span data-stu-id="8ad84-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8ad84-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="8ad84-104">Suggestion</span></span>

<span data-ttu-id="8ad84-105">После выполнения одного дополнительного шага в отладчике локальные значения или значения поля корректно обновляются.</span><span class="sxs-lookup"><span data-stu-id="8ad84-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="8ad84-106">Эта проблема также была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="8ad84-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="8ad84-107">name</span><span class="sxs-lookup"><span data-stu-id="8ad84-107">Name</span></span>    | <span data-ttu-id="8ad84-108">Значение</span><span class="sxs-lookup"><span data-stu-id="8ad84-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8ad84-109">Область</span><span class="sxs-lookup"><span data-stu-id="8ad84-109">Scope</span></span>   |<span data-ttu-id="8ad84-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="8ad84-110">Edge</span></span>|
|<span data-ttu-id="8ad84-111">Version</span><span class="sxs-lookup"><span data-stu-id="8ad84-111">Version</span></span>|<span data-ttu-id="8ad84-112">4.5</span><span class="sxs-lookup"><span data-stu-id="8ad84-112">4.5</span></span>|
|<span data-ttu-id="8ad84-113">Type</span><span class="sxs-lookup"><span data-stu-id="8ad84-113">Type</span></span>|<span data-ttu-id="8ad84-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="8ad84-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8ad84-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="8ad84-115">Affected APIs</span></span>

<span data-ttu-id="8ad84-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="8ad84-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
