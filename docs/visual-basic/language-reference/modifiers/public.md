---
title: Общие
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35332e50227cdef6386362df17c10b5b2cdaa689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415353"
---
# <a name="public-visual-basic"></a><span data-ttu-id="62dbd-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62dbd-102">Public (Visual Basic)</span></span>
<span data-ttu-id="62dbd-103">Указывает, что один или несколько объявленных программных элементов не имеют ограничений доступа.</span><span class="sxs-lookup"><span data-stu-id="62dbd-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62dbd-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="62dbd-104">Remarks</span></span>  
 <span data-ttu-id="62dbd-105">При публикации компонента или набора компонентов, таких как библиотека классов, обычно требуется, чтобы элементы программирования были доступны любому коду, взаимодействующему со сборкой.</span><span class="sxs-lookup"><span data-stu-id="62dbd-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="62dbd-106">Чтобы обеспечить такой неограниченный доступ к элементу, его можно объявить с помощью `Public` .</span><span class="sxs-lookup"><span data-stu-id="62dbd-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="62dbd-107">Открытый доступ является обычным уровнем для программного элемента, если нет необходимости ограничивать доступ к нему.</span><span class="sxs-lookup"><span data-stu-id="62dbd-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="62dbd-108">Обратите внимание, что уровень доступа элемента, объявленного в интерфейсе, модуле, классе или структуре, по умолчанию имеет значение `Public` , если вы не объявили его в противном случае.</span><span class="sxs-lookup"><span data-stu-id="62dbd-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="62dbd-109">Правила</span><span class="sxs-lookup"><span data-stu-id="62dbd-109">Rules</span></span>  
  
- <span data-ttu-id="62dbd-110">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="62dbd-110">**Declaration Context.**</span></span> <span data-ttu-id="62dbd-111">Можно использовать `Public` только на уровне модуля, интерфейса или пространства имен.</span><span class="sxs-lookup"><span data-stu-id="62dbd-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="62dbd-112">Это означает, что контекст объявления для `Public` элемента должен быть исходным файлом, пространством имен, интерфейсом, модулем, классом или структурой и не может быть процедурой.</span><span class="sxs-lookup"><span data-stu-id="62dbd-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="62dbd-113">Поведение</span><span class="sxs-lookup"><span data-stu-id="62dbd-113">Behavior</span></span>  
  
- <span data-ttu-id="62dbd-114">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="62dbd-114">**Access Level.**</span></span> <span data-ttu-id="62dbd-115">Весь код, который может получить доступ к модулю, классу или структуре, может получить доступ к его `Public` элементам.</span><span class="sxs-lookup"><span data-stu-id="62dbd-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="62dbd-116">**Доступ по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="62dbd-116">**Default Access.**</span></span> <span data-ttu-id="62dbd-117">Локальные переменные в процедуре по умолчанию имеют открытый доступ, и в них нельзя использовать какие-либо модификаторы доступа.</span><span class="sxs-lookup"><span data-stu-id="62dbd-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="62dbd-118">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="62dbd-118">**Access Modifiers.**</span></span> <span data-ttu-id="62dbd-119">Ключевые слова, определяющие уровень доступа, называются *модификаторами доступа*.</span><span class="sxs-lookup"><span data-stu-id="62dbd-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="62dbd-120">Сравнение модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="62dbd-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="62dbd-121">Модификатор `Public` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="62dbd-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="62dbd-122">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="62dbd-122">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="62dbd-123">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="62dbd-123">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="62dbd-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="62dbd-124">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="62dbd-125">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="62dbd-125">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="62dbd-126">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="62dbd-126">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="62dbd-127">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="62dbd-127">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="62dbd-128">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="62dbd-128">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="62dbd-129">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="62dbd-129">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="62dbd-130">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="62dbd-130">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="62dbd-131">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="62dbd-131">Module Statement</span></span>](../statements/module-statement.md)  
  
 [<span data-ttu-id="62dbd-132">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="62dbd-132">Operator Statement</span></span>](../statements/operator-statement.md)  
  
 [<span data-ttu-id="62dbd-133">Property Statement</span><span class="sxs-lookup"><span data-stu-id="62dbd-133">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="62dbd-134">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="62dbd-134">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="62dbd-135">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="62dbd-135">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="62dbd-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="62dbd-136">See also</span></span>

- [<span data-ttu-id="62dbd-137">От</span><span class="sxs-lookup"><span data-stu-id="62dbd-137">Protected</span></span>](protected.md)
- [<span data-ttu-id="62dbd-138">Объявление</span><span class="sxs-lookup"><span data-stu-id="62dbd-138">Friend</span></span>](friend.md)
- [<span data-ttu-id="62dbd-139">Частное</span><span class="sxs-lookup"><span data-stu-id="62dbd-139">Private</span></span>](private.md)
- [<span data-ttu-id="62dbd-140">Частный защищенный</span><span class="sxs-lookup"><span data-stu-id="62dbd-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="62dbd-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="62dbd-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="62dbd-142">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62dbd-142">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="62dbd-143">Процедуры</span><span class="sxs-lookup"><span data-stu-id="62dbd-143">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="62dbd-144">Структуры</span><span class="sxs-lookup"><span data-stu-id="62dbd-144">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="62dbd-145">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="62dbd-145">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
