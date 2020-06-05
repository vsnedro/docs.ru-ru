---
title: Переопределения
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 657f838b2959a5b6a7cef5ff18295a4ada709e9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392032"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="3cb78-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cb78-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="3cb78-103">Указывает, что свойство или процедура переопределяет свойство или процедуру с идентичным названием, унаследованную от базового класса.</span><span class="sxs-lookup"><span data-stu-id="3cb78-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="3cb78-104">Правила</span><span class="sxs-lookup"><span data-stu-id="3cb78-104">Rules</span></span>

- <span data-ttu-id="3cb78-105">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="3cb78-105">**Declaration Context.**</span></span> <span data-ttu-id="3cb78-106">Можно использовать `Overrides` только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="3cb78-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="3cb78-107">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="3cb78-107">**Combined Modifiers.**</span></span> <span data-ttu-id="3cb78-108">Нельзя указывать `Overrides` вместе с `Shadows` или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="3cb78-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="3cb78-109">Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="3cb78-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="3cb78-110">**Соответствие сигнатур.**</span><span class="sxs-lookup"><span data-stu-id="3cb78-110">**Matching Signatures.**</span></span> <span data-ttu-id="3cb78-111">Сигнатура этого объявления должна точно совпадать с *сигнатурой* свойства или процедуры, которую он переопределяет.</span><span class="sxs-lookup"><span data-stu-id="3cb78-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="3cb78-112">Это означает, что списки параметров должны содержать одинаковое число параметров, в том же порядке и с теми же типами данных.</span><span class="sxs-lookup"><span data-stu-id="3cb78-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="3cb78-113">Помимо сигнатуры, для объявления переопределения должны также совпадать следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="3cb78-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="3cb78-114">уровень доступа;</span><span class="sxs-lookup"><span data-stu-id="3cb78-114">The access level</span></span>

  - <span data-ttu-id="3cb78-115">тип возвращаемого значения (если применимо).</span><span class="sxs-lookup"><span data-stu-id="3cb78-115">The return type, if any</span></span>

- <span data-ttu-id="3cb78-116">**Универсальные сигнатуры.**</span><span class="sxs-lookup"><span data-stu-id="3cb78-116">**Generic Signatures.**</span></span> <span data-ttu-id="3cb78-117">Для универсальной процедуры сигнатура содержит число параметров типа.</span><span class="sxs-lookup"><span data-stu-id="3cb78-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="3cb78-118">Поэтому объявление переопределения должно соответствовать версии базового класса и в этом аспекте.</span><span class="sxs-lookup"><span data-stu-id="3cb78-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="3cb78-119">**Дополнительные соответствия.**</span><span class="sxs-lookup"><span data-stu-id="3cb78-119">**Additional Matching.**</span></span> <span data-ttu-id="3cb78-120">Помимо соответствия сигнатуры версии базового класса, это объявление должно также соответствовать ему в следующих аспектах:</span><span class="sxs-lookup"><span data-stu-id="3cb78-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="3cb78-121">Модификатор уровня доступа (например, [Public](public.md))</span><span class="sxs-lookup"><span data-stu-id="3cb78-121">Access-level modifier (such as [Public](public.md))</span></span>

  - <span data-ttu-id="3cb78-122">Механизм передачи каждого параметра ([ByVal](byval.md) или [ByRef](byref.md))</span><span class="sxs-lookup"><span data-stu-id="3cb78-122">Passing mechanism of each parameter ([ByVal](byval.md) or [ByRef](byref.md))</span></span>

  - <span data-ttu-id="3cb78-123">списки ограничений для каждого типа параметра универсальной процедуры.</span><span class="sxs-lookup"><span data-stu-id="3cb78-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="3cb78-124">**Сокрытие и переопределение.**</span><span class="sxs-lookup"><span data-stu-id="3cb78-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="3cb78-125">Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="3cb78-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="3cb78-126">Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="3cb78-126">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="3cb78-127">При использовании `Overrides` компилятор неявно добавляет `Overloads`, чтобы упростить работу API-интерфейсов с библиотекой C#.</span><span class="sxs-lookup"><span data-stu-id="3cb78-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="3cb78-128">Модификатор `Overrides` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="3cb78-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="3cb78-129">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="3cb78-129">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="3cb78-130">Property Statement</span><span class="sxs-lookup"><span data-stu-id="3cb78-130">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="3cb78-131">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="3cb78-131">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="3cb78-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3cb78-132">See also</span></span>

- [<span data-ttu-id="3cb78-133">MustOverride</span><span class="sxs-lookup"><span data-stu-id="3cb78-133">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="3cb78-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="3cb78-134">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="3cb78-135">Overridable</span><span class="sxs-lookup"><span data-stu-id="3cb78-135">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="3cb78-136">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3cb78-136">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="3cb78-137">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3cb78-137">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="3cb78-138">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3cb78-138">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="3cb78-139">Type List</span><span class="sxs-lookup"><span data-stu-id="3cb78-139">Type List</span></span>](../statements/type-list.md)
