---
ms.openlocfilehash: 9a2d6a25a8ab1b8bf65b947557802e0805a7f826
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617276"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a><span data-ttu-id="32388-101">Переменная-итератор Foreach теперь ограничена областью итерации, поэтому используется другая семантика захвата замыкания (в C# 5)</span><span class="sxs-lookup"><span data-stu-id="32388-101">Foreach iterator variable is now scoped within the iteration, so closure capturing semantics are different (in C#5)</span></span>

#### <a name="details"></a><span data-ttu-id="32388-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="32388-102">Details</span></span>

<span data-ttu-id="32388-103">Начиная с C# 5 (Visual Studio 2012) переменные-итераторы `foreach` действуют в рамках итерации.</span><span class="sxs-lookup"><span data-stu-id="32388-103">Beginning with C# 5 (Visual Studio 2012), `foreach` iterator variables are scoped within the iteration.</span></span> <span data-ttu-id="32388-104">Это может привести к нарушению работы, если код ранее зависел от переменных, не включаемых в замыкание `foreach`.</span><span class="sxs-lookup"><span data-stu-id="32388-104">This can cause breaks if code was previously depending on the variables to not be included in the `foreach`'s closure.</span></span> <span data-ttu-id="32388-105">Признаком этого изменения будет то, что переменная-итератор, переданная делегату, будет рассматриваться как значение, существовавшее во время создания делегата, а не как значение, которое существовало во время вызова делегата.</span><span class="sxs-lookup"><span data-stu-id="32388-105">The symptom of this change is that an iterator variable passed to a delegate is treated as the value it has at the time the delegate is created, rather than the value it has at the time the delegate is invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="32388-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="32388-106">Suggestion</span></span>

<span data-ttu-id="32388-107">В идеале следует обновить код для ожидания нового поведения компилятора.</span><span class="sxs-lookup"><span data-stu-id="32388-107">Ideally, code should be updated to expect the new compiler behavior.</span></span> <span data-ttu-id="32388-108">Если требуются старые семантики, переменную-итератор можно заменить отдельной переменной, которая явным образом помещается за пределами области цикла.</span><span class="sxs-lookup"><span data-stu-id="32388-108">If the old semantics are required, the iterator variable can be replaced with a separate variable which is explicitly placed outside of the loop's scope.</span></span>

| <span data-ttu-id="32388-109">name</span><span class="sxs-lookup"><span data-stu-id="32388-109">Name</span></span>    | <span data-ttu-id="32388-110">Значение</span><span class="sxs-lookup"><span data-stu-id="32388-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="32388-111">Область</span><span class="sxs-lookup"><span data-stu-id="32388-111">Scope</span></span>   | <span data-ttu-id="32388-112">Значительно</span><span class="sxs-lookup"><span data-stu-id="32388-112">Major</span></span>       |
| <span data-ttu-id="32388-113">Version</span><span class="sxs-lookup"><span data-stu-id="32388-113">Version</span></span> | <span data-ttu-id="32388-114">4.5</span><span class="sxs-lookup"><span data-stu-id="32388-114">4.5</span></span>         |
| <span data-ttu-id="32388-115">Type</span><span class="sxs-lookup"><span data-stu-id="32388-115">Type</span></span>    | <span data-ttu-id="32388-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="32388-116">Retargeting</span></span> |
