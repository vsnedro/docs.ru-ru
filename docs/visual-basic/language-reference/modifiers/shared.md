---
title: Shared
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: 000cc13bc6e80914e9a21b6ee60e91127809ee08
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307089"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="bcc73-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcc73-102">Shared (Visual Basic)</span></span>

<span data-ttu-id="bcc73-103">Указывает, что один или несколько объявленных программных элементов связаны с классом или структурой в большом объеме, а не с конкретным экземпляром класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="bcc73-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>

## <a name="when-to-use-shared"></a><span data-ttu-id="bcc73-104">Когда следует использовать Shared</span><span class="sxs-lookup"><span data-stu-id="bcc73-104">When to Use Shared</span></span>

<span data-ttu-id="bcc73-105">Совместное использование члена класса или структуры делает его доступным для каждого экземпляра, а не для *общего доступа*, где каждый экземпляр хранит собственную копию.</span><span class="sxs-lookup"><span data-stu-id="bcc73-105">Sharing a member of a class or structure makes it available to every instance, rather than *non-shared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="bcc73-106">Это полезно, например, если значение переменной применяется ко всему приложению.</span><span class="sxs-lookup"><span data-stu-id="bcc73-106">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="bcc73-107">Если объявить эту переменную как `Shared` , то все экземпляры получают доступ к тому же месту хранения, и если один экземпляр изменяет значение переменной, все экземпляры получают доступ к обновленному значению.</span><span class="sxs-lookup"><span data-stu-id="bcc73-107">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>

<span data-ttu-id="bcc73-108">Совместное использование не изменяет уровень доступа элемента.</span><span class="sxs-lookup"><span data-stu-id="bcc73-108">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="bcc73-109">Например, член класса может быть общим и частным (доступным только в пределах класса), а также не является общим и открытым.</span><span class="sxs-lookup"><span data-stu-id="bcc73-109">For example, a class member can be shared and private (accessible only from within the class), or non-shared and public.</span></span> <span data-ttu-id="bcc73-110">Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="bcc73-110">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

## <a name="rules"></a><span data-ttu-id="bcc73-111">Правила</span><span class="sxs-lookup"><span data-stu-id="bcc73-111">Rules</span></span>

- <span data-ttu-id="bcc73-112">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="bcc73-112">**Declaration Context.**</span></span> <span data-ttu-id="bcc73-113">`Shared` можно использовать только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="bcc73-113">You can use `Shared` only at module level.</span></span> <span data-ttu-id="bcc73-114">Это означает, что контекст объявления для `Shared` элемента должен быть классом или структурой и не может быть исходным файлом, пространством имен или процедурой.</span><span class="sxs-lookup"><span data-stu-id="bcc73-114">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="bcc73-115">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="bcc73-115">**Combined Modifiers.**</span></span> <span data-ttu-id="bcc73-116">Нельзя указывать `Shared` вместе с [переопределениями](../../../visual-basic/language-reference/modifiers/overrides.md), [переопределяемыми](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)или [static](../../../visual-basic/language-reference/modifiers/static.md) в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="bcc73-116">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>

- <span data-ttu-id="bcc73-117">**Данному.**</span><span class="sxs-lookup"><span data-stu-id="bcc73-117">**Accessing.**</span></span> <span data-ttu-id="bcc73-118">Доступ к общему элементу осуществляется путем указания его имени класса или структуры, а не имени переменной определенного экземпляра его класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="bcc73-118">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="bcc73-119">Вам даже не нужно создавать экземпляр класса или структуры для доступа к его общим членам.</span><span class="sxs-lookup"><span data-stu-id="bcc73-119">You do not even have to create an instance of a class or structure to access its shared members.</span></span>

     <span data-ttu-id="bcc73-120">В следующем примере вызывается общая процедура, <xref:System.Double.IsNaN%2A> предоставляемая <xref:System.Double> структурой.</span><span class="sxs-lookup"><span data-stu-id="bcc73-120">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- <span data-ttu-id="bcc73-121">**Неявный общий доступ.**</span><span class="sxs-lookup"><span data-stu-id="bcc73-121">**Implicit Sharing.**</span></span> <span data-ttu-id="bcc73-122">Нельзя использовать `Shared` Модификатор в [операторе const](../../../visual-basic/language-reference/statements/const-statement.md), но константы неявно являются общими.</span><span class="sxs-lookup"><span data-stu-id="bcc73-122">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="bcc73-123">Аналогичным образом нельзя объявить член модуля или интерфейса `Shared` , но они являются неявно общими.</span><span class="sxs-lookup"><span data-stu-id="bcc73-123">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>

## <a name="behavior"></a><span data-ttu-id="bcc73-124">Поведение</span><span class="sxs-lookup"><span data-stu-id="bcc73-124">Behavior</span></span>

- <span data-ttu-id="bcc73-125">**Объема.**</span><span class="sxs-lookup"><span data-stu-id="bcc73-125">**Storage.**</span></span> <span data-ttu-id="bcc73-126">Общая переменная или событие хранится в памяти только один раз, независимо от того, сколько экземпляров вы создаете его класс или структуру.</span><span class="sxs-lookup"><span data-stu-id="bcc73-126">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="bcc73-127">Аналогично, Общая процедура или свойство содержит только один набор локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="bcc73-127">Similarly, a shared procedure or property holds only one set of local variables.</span></span>

- <span data-ttu-id="bcc73-128">**Доступ через переменную экземпляра.**</span><span class="sxs-lookup"><span data-stu-id="bcc73-128">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="bcc73-129">Доступ к общему элементу можно получить, добавив в него имя переменной, содержащей конкретный экземпляр его класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="bcc73-129">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="bcc73-130">Несмотря на то, что обычно работает, как и ожидалось, компилятор создает предупреждающее сообщение и предоставляет доступ через имя класса или структуры вместо переменной.</span><span class="sxs-lookup"><span data-stu-id="bcc73-130">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>

- <span data-ttu-id="bcc73-131">**Доступ через выражение экземпляра.**</span><span class="sxs-lookup"><span data-stu-id="bcc73-131">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="bcc73-132">При доступе к общему элементу с помощью выражения, возвращающего экземпляр класса или структуры, компилятор делает доступ через имя класса или структуры вместо вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="bcc73-132">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="bcc73-133">Это приводит к непредвиденным результатам, если выражение предназначено для выполнения других действий, а также для возврата экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bcc73-133">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="bcc73-134">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bcc73-134">The following example illustrates this.</span></span>
  
    ```vb
    Sub Main()
        ' The following line is the preferred way to access Total.
        ShareTotal.Total = 10

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of through
        ' the variable instanceVar. This works as expected and adds
        ' 100 to Total.
        Dim instanceVar As New ShareTotal
        instanceVar.Total += 100

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of calling
        ' ReturnClass(). This adds 1000 to total but does not work as
        ' expected, because the WriteLine in ReturnClass() does not run.
        Console.WriteLine("Value of total is " & CStr(ShareTotal.Total))
        ReturnClass().Total += 1000
    End Sub

    Public Function ReturnClass() As ShareTotal
        Console.WriteLine("Function ReturnClass() called")
        Return New ShareTotal
    End Function

    Public Class ShareTotal
        Public Shared Property Total As Integer
    End Class
    ```

     <span data-ttu-id="bcc73-135">В предыдущем примере компилятор выдает предупреждающее сообщение в обоих случаях, когда код обращается к общему свойству `Total` через экземпляр.</span><span class="sxs-lookup"><span data-stu-id="bcc73-135">In the preceding example, the compiler generates a warning message both times the code accesses the shared property `Total` through an instance.</span></span> <span data-ttu-id="bcc73-136">В каждом случае он предоставляет доступ напрямую через класс и не `ShareTotal` использует ни одного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bcc73-136">In each case it makes the access directly through the class `ShareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="bcc73-137">В случае предполагаемого вызова процедуры `ReturnClass` это означает, что он даже не создает вызов `ReturnClass` , поэтому не выполняется дополнительное действие отображения "функция ретурнкласс ()".</span><span class="sxs-lookup"><span data-stu-id="bcc73-137">In the case of the intended call to the procedure `ReturnClass`, this means it does not even generate a call to `ReturnClass`, so the additional action of displaying "Function ReturnClass() called" is not performed.</span></span>

<span data-ttu-id="bcc73-138">Модификатор `Shared` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="bcc73-138">The `Shared` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="bcc73-139">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="bcc73-139">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="bcc73-140">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="bcc73-140">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="bcc73-141">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="bcc73-141">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="bcc73-142">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="bcc73-142">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="bcc73-143">Property Statement</span><span class="sxs-lookup"><span data-stu-id="bcc73-143">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="bcc73-144">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="bcc73-144">Sub Statement</span></span>](../statements/sub-statement.md)
  
## <a name="see-also"></a><span data-ttu-id="bcc73-145">См. также</span><span class="sxs-lookup"><span data-stu-id="bcc73-145">See also</span></span>

- [<span data-ttu-id="bcc73-146">Shadows</span><span class="sxs-lookup"><span data-stu-id="bcc73-146">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="bcc73-147">Статически</span><span class="sxs-lookup"><span data-stu-id="bcc73-147">Static</span></span>](static.md)
- [<span data-ttu-id="bcc73-148">Время существования в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bcc73-148">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="bcc73-149">Процедуры</span><span class="sxs-lookup"><span data-stu-id="bcc73-149">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="bcc73-150">Структуры</span><span class="sxs-lookup"><span data-stu-id="bcc73-150">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="bcc73-151">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="bcc73-151">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
