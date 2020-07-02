---
ms.openlocfilehash: 907c4aa5573c392a68afad0a4d937eadcd556440
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620607"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="725d0-101">Значения NULL операции объединения отображаются в отладчике с запаздыванием на один шаг</span><span class="sxs-lookup"><span data-stu-id="725d0-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="725d0-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="725d0-102">Details</span></span>

<span data-ttu-id="725d0-103">Из-за ошибки в .NET Framework 4.5 значения, заданные с использованием операции объединения NULL, не отображаются в отладчике немедленно после выполнения операции присваивания в 64-разрядной версии платформы.</span><span class="sxs-lookup"><span data-stu-id="725d0-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="725d0-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="725d0-104">Suggestion</span></span>

<span data-ttu-id="725d0-105">После выполнения одного дополнительного шага в отладчике локальные значения или значения поля корректно обновляются.</span><span class="sxs-lookup"><span data-stu-id="725d0-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="725d0-106">Эта проблема также была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="725d0-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="725d0-107">name</span><span class="sxs-lookup"><span data-stu-id="725d0-107">Name</span></span>    | <span data-ttu-id="725d0-108">Значение</span><span class="sxs-lookup"><span data-stu-id="725d0-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="725d0-109">Область</span><span class="sxs-lookup"><span data-stu-id="725d0-109">Scope</span></span>   |<span data-ttu-id="725d0-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="725d0-110">Edge</span></span>|
|<span data-ttu-id="725d0-111">Version</span><span class="sxs-lookup"><span data-stu-id="725d0-111">Version</span></span>|<span data-ttu-id="725d0-112">4.5</span><span class="sxs-lookup"><span data-stu-id="725d0-112">4.5</span></span>|
|<span data-ttu-id="725d0-113">Type</span><span class="sxs-lookup"><span data-stu-id="725d0-113">Type</span></span>|<span data-ttu-id="725d0-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="725d0-114">Runtime</span></span>|
