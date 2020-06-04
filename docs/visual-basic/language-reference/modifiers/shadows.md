---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: 7aed6bec21bd484cca019b061bd5915de13a9eb8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402711"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="9c6e3-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c6e3-102">Shadows (Visual Basic)</span></span>

<span data-ttu-id="9c6e3-103">Указывает, что объявленный программный элемент повторно объявляет и скрывает элемент с идентичным именем или набор перегруженных элементов в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c6e3-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9c6e3-104">Remarks</span></span>

<span data-ttu-id="9c6e3-105">Основное назначение теневого копирования (которое также называется *скрытием по имени*) — сохранение определения членов класса.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="9c6e3-106">Базовый класс может быть подвергнут изменениям, создающим элемент с тем же именем, что и у уже определенного.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="9c6e3-107">В этом случае `Shadows` Модификатор принудительно определяет ссылки через класс на определенный член, а не на новый элемент базового класса.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>

<span data-ttu-id="9c6e3-108">Сокрытие и переопределение заменяют наследуемый элемент, но между этими подходами существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="9c6e3-109">Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="9c6e3-109">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>

## <a name="rules"></a><span data-ttu-id="9c6e3-110">Правила</span><span class="sxs-lookup"><span data-stu-id="9c6e3-110">Rules</span></span>

- <span data-ttu-id="9c6e3-111">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="9c6e3-111">**Declaration Context.**</span></span> <span data-ttu-id="9c6e3-112">Можно использовать `Shadows` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="9c6e3-113">Это означает, что контекст объявления для `Shadows` элемента должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

  <span data-ttu-id="9c6e3-114">В одном операторе объявления можно объявить только один элемент с тенью.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-114">You can declare only one shadowing element in a single declaration statement.</span></span>

- <span data-ttu-id="9c6e3-115">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="9c6e3-115">**Combined Modifiers.**</span></span> <span data-ttu-id="9c6e3-116">Нельзя указывать `Shadows` вместе с `Overloads` , `Overrides` или `Static` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>

- <span data-ttu-id="9c6e3-117">**Типы элементов.**</span><span class="sxs-lookup"><span data-stu-id="9c6e3-117">**Element Types.**</span></span> <span data-ttu-id="9c6e3-118">Можно скрыть любой тип объявленного элемента, используя любой другой тип.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="9c6e3-119">При скрытии свойства или процедуры с другим свойством или процедурой параметры и тип возвращаемого значения не должны совпадать с параметрами в свойстве или процедуре базового класса.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>

- <span data-ttu-id="9c6e3-120">**Данному.**</span><span class="sxs-lookup"><span data-stu-id="9c6e3-120">**Accessing.**</span></span> <span data-ttu-id="9c6e3-121">Затененный элемент в базовом классе обычно недоступен в производном классе, который его затеняет.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="9c6e3-122">Однако применимы следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-122">However, the following considerations apply.</span></span>

  - <span data-ttu-id="9c6e3-123">Если элемент теневого копирования недоступен из кода, ссылающегося на него, ссылка разрешается в затененный элемент.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="9c6e3-124">Например, если `Private` элемент затеняет элемент базового класса, код, который не имеет разрешения на доступ к `Private` элементу, обращается к элементу базового класса.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>

  - <span data-ttu-id="9c6e3-125">При скрытии элемента доступ к затененному элементу по-прежнему можно получить через объект, объявленный с типом базового класса.</span><span class="sxs-lookup"><span data-stu-id="9c6e3-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="9c6e3-126">Доступ к нему также можно получить с помощью `MyBase` .</span><span class="sxs-lookup"><span data-stu-id="9c6e3-126">You can also access it through `MyBase`.</span></span>

<span data-ttu-id="9c6e3-127">Модификатор `Shadows` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="9c6e3-127">The `Shadows` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="9c6e3-128">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="9c6e3-128">Class Statement</span></span>](../statements/class-statement.md)

- [<span data-ttu-id="9c6e3-129">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="9c6e3-129">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="9c6e3-130">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="9c6e3-130">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="9c6e3-131">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="9c6e3-131">Delegate Statement</span></span>](../statements/delegate-statement.md)

- [<span data-ttu-id="9c6e3-132">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="9c6e3-132">Dim Statement</span></span>](../statements/dim-statement.md)

- [<span data-ttu-id="9c6e3-133">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="9c6e3-133">Enum Statement</span></span>](../statements/enum-statement.md)

- [<span data-ttu-id="9c6e3-134">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="9c6e3-134">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="9c6e3-135">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="9c6e3-135">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="9c6e3-136">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="9c6e3-136">Interface Statement</span></span>](../statements/interface-statement.md)

- [<span data-ttu-id="9c6e3-137">Property Statement</span><span class="sxs-lookup"><span data-stu-id="9c6e3-137">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="9c6e3-138">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="9c6e3-138">Structure Statement</span></span>](../statements/structure-statement.md)

- [<span data-ttu-id="9c6e3-139">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="9c6e3-139">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="9c6e3-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9c6e3-140">See also</span></span>

- [<span data-ttu-id="9c6e3-141">Общий</span><span class="sxs-lookup"><span data-stu-id="9c6e3-141">Shared</span></span>](shared.md)
- [<span data-ttu-id="9c6e3-142">Статическое</span><span class="sxs-lookup"><span data-stu-id="9c6e3-142">Static</span></span>](static.md)
- [<span data-ttu-id="9c6e3-143">Частное</span><span class="sxs-lookup"><span data-stu-id="9c6e3-143">Private</span></span>](private.md)
- [<span data-ttu-id="9c6e3-144">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="9c6e3-144">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="9c6e3-145">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="9c6e3-145">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="9c6e3-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="9c6e3-146">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="9c6e3-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="9c6e3-147">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="9c6e3-148">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="9c6e3-148">Overloads</span></span>](overloads.md)
- [<span data-ttu-id="9c6e3-149">Overridable</span><span class="sxs-lookup"><span data-stu-id="9c6e3-149">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="9c6e3-150">Переопределения</span><span class="sxs-lookup"><span data-stu-id="9c6e3-150">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="9c6e3-151">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9c6e3-151">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
