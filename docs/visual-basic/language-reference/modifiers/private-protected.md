---
title: Частный защищенный
ms.date: 05/10/2018
f1_keywords:
- vb.PrivateProtected
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 8ad1509da71bc80b33700d363ddd4569a0965dff
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303469"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="f1507-102">Частный защищенный (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1507-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="f1507-103">Комбинация ключевых слов `Private Protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="f1507-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="f1507-104">`Private Protected`Элемент доступен для всех элементов в содержащем его классе, а также по типам, производным от содержащего класса, но только в том случае, если они находятся в содержащей его сборке.</span><span class="sxs-lookup"><span data-stu-id="f1507-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="f1507-105">Можно указать `Private Protected` только для членов классов. нельзя применять `Private Protected` к членам структуры, поскольку структуры не наследуются.</span><span class="sxs-lookup"><span data-stu-id="f1507-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="f1507-106">`Private Protected`Модификатор доступа поддерживается Visual Basic 15,5 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f1507-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="f1507-107">Чтобы использовать его, можно добавить в файл проекта Visual Basic (VBPROJ) следующий элемент \* .</span><span class="sxs-lookup"><span data-stu-id="f1507-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="f1507-108">Если в системе установлен Visual Basic 15,5 или более поздней версии, он позволяет воспользоваться всеми возможностями языка, поддерживаемыми последней версией компилятора Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f1507-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="f1507-109">Дополнительные сведения см. [в разделе Задание языковой версии Visual Basic](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="f1507-109">For more information see [setting the Visual Basic language version](../configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f1507-110">В Visual Studio выбор справки F1 `private protected` для предоставляет справку как для [частного](private.md) , так и для [защищенного](protected.md).</span><span class="sxs-lookup"><span data-stu-id="f1507-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="f1507-111">Интегрированная среда разработки выбирает один маркер под курсором, а не составное слово.</span><span class="sxs-lookup"><span data-stu-id="f1507-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="f1507-112">Правила</span><span class="sxs-lookup"><span data-stu-id="f1507-112">Rules</span></span>

- <span data-ttu-id="f1507-113">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="f1507-113">**Declaration Context.**</span></span> <span data-ttu-id="f1507-114">Можно использовать `Private Protected` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="f1507-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="f1507-115">Это означает, что контекст объявления для `Protected` элемента должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.</span><span class="sxs-lookup"><span data-stu-id="f1507-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="f1507-116">Поведение</span><span class="sxs-lookup"><span data-stu-id="f1507-116">Behavior</span></span>

- <span data-ttu-id="f1507-117">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="f1507-117">**Access Level.**</span></span> <span data-ttu-id="f1507-118">Весь код в классе может обращаться к его элементам.</span><span class="sxs-lookup"><span data-stu-id="f1507-118">All code in a class can access its elements.</span></span> <span data-ttu-id="f1507-119">Код в любом классе, производном от базового класса и содержащийся в той же сборке, имеет доступ ко всем `Private Protected` элементам базового класса.</span><span class="sxs-lookup"><span data-stu-id="f1507-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="f1507-120">Однако код в любом классе, производном от базового класса и содержащийся в другой сборке, не может получить доступ к элементам базового класса `Private Protected` .</span><span class="sxs-lookup"><span data-stu-id="f1507-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="f1507-121">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="f1507-121">**Access Modifiers.**</span></span> <span data-ttu-id="f1507-122">Ключевые слова, определяющие уровень доступа, называются *модификаторами доступа*.</span><span class="sxs-lookup"><span data-stu-id="f1507-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="f1507-123">Сравнение модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f1507-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="f1507-124">Модификатор `Private Protected` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="f1507-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="f1507-125">[Оператор Class](../statements/class-statement.md) вложенного класса</span><span class="sxs-lookup"><span data-stu-id="f1507-125">[Class Statement](../statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="f1507-126">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="f1507-126">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="f1507-127">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="f1507-127">Declare Statement</span></span>](../statements/declare-statement.md)

- <span data-ttu-id="f1507-128">[Оператор Delegate](../statements/delegate-statement.md) делегата, вложенного в класс</span><span class="sxs-lookup"><span data-stu-id="f1507-128">[Delegate Statement](../statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="f1507-129">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="f1507-129">Dim Statement</span></span>](../statements/dim-statement.md)

- <span data-ttu-id="f1507-130">[Оператор Enum](../statements/enum-statement.md) перечисления, вложенного в класс</span><span class="sxs-lookup"><span data-stu-id="f1507-130">[Enum Statement](../statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="f1507-131">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="f1507-131">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="f1507-132">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="f1507-132">Function Statement</span></span>](../statements/function-statement.md)

- <span data-ttu-id="f1507-133">[Оператор Interface](../statements/interface-statement.md) интерфейса, вложенного в класс</span><span class="sxs-lookup"><span data-stu-id="f1507-133">[Interface Statement](../statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="f1507-134">Property Statement</span><span class="sxs-lookup"><span data-stu-id="f1507-134">Property Statement</span></span>](../statements/property-statement.md)

- <span data-ttu-id="f1507-135">[Оператор Structure](../statements/structure-statement.md) структуры, вложенной в класс</span><span class="sxs-lookup"><span data-stu-id="f1507-135">[Structure Statement](../statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="f1507-136">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="f1507-136">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="f1507-137">См. также</span><span class="sxs-lookup"><span data-stu-id="f1507-137">See also</span></span>

- [<span data-ttu-id="f1507-138">Открытый</span><span class="sxs-lookup"><span data-stu-id="f1507-138">Public</span></span>](public.md)
- [<span data-ttu-id="f1507-139">От</span><span class="sxs-lookup"><span data-stu-id="f1507-139">Protected</span></span>](protected.md)
- [<span data-ttu-id="f1507-140">Объявление</span><span class="sxs-lookup"><span data-stu-id="f1507-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="f1507-141">Частное</span><span class="sxs-lookup"><span data-stu-id="f1507-141">Private</span></span>](private.md)
- [<span data-ttu-id="f1507-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="f1507-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="f1507-143">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1507-143">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="f1507-144">Процедуры</span><span class="sxs-lookup"><span data-stu-id="f1507-144">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="f1507-145">Структуры</span><span class="sxs-lookup"><span data-stu-id="f1507-145">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="f1507-146">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="f1507-146">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
