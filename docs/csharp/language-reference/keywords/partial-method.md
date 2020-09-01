---
description: Справочник по C#. Метод partial
title: Справочник по C#. Метод partial
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: d6c433fd30f6ec51355bdefee90d815783487c1b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134384"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="93ae1-103">Метод partial (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="93ae1-103">partial method (C# Reference)</span></span>

<span data-ttu-id="93ae1-104">Сигнатура разделяемого метода определяется в одной части разделяемого типа, а его реализация — в другой части этого типа.</span><span class="sxs-lookup"><span data-stu-id="93ae1-104">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="93ae1-105">С помощью разделяемых методов разработчики классов могут при необходимости реализовывать ловушки методов, которые схожи с обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="93ae1-105">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="93ae1-106">Если реализация не предоставлена, компилятор удаляет сигнатуру во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="93ae1-106">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="93ae1-107">В отношении разделяемых методов применяются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="93ae1-107">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="93ae1-108">Сигнатуры в обеих частях разделяемого типа должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="93ae1-108">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="93ae1-109">Метод должен возвращать значение void.</span><span class="sxs-lookup"><span data-stu-id="93ae1-109">The method must return void.</span></span>

- <span data-ttu-id="93ae1-110">Модификаторы доступа не допускаются.</span><span class="sxs-lookup"><span data-stu-id="93ae1-110">No access modifiers are allowed.</span></span> <span data-ttu-id="93ae1-111">Разделяемые методы являются неявно частными.</span><span class="sxs-lookup"><span data-stu-id="93ae1-111">Partial methods are implicitly private.</span></span>

<span data-ttu-id="93ae1-112">В следующем примере показан разделяемый метод, определенный в двух частях разделяемого класса:</span><span class="sxs-lookup"><span data-stu-id="93ae1-112">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="93ae1-113">Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="93ae1-113">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="93ae1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="93ae1-114">See also</span></span>

- [<span data-ttu-id="93ae1-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="93ae1-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="93ae1-116">Тип partial</span><span class="sxs-lookup"><span data-stu-id="93ae1-116">partial type</span></span>](partial-type.md)
