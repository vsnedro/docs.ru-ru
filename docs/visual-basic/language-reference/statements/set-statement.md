---
title: Оператор Set
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: b3524769567a56a87184bf916a3e5ccb1fd4fa1c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871757"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="3648a-102">Инструкция Set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3648a-102">Set Statement (Visual Basic)</span></span>

<span data-ttu-id="3648a-103">Объявляет `Set` процедуру свойства, используемую для присвоения значения свойству.</span><span class="sxs-lookup"><span data-stu-id="3648a-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3648a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3648a-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="3648a-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="3648a-105">Parts</span></span>  

 `attributelist`  
 <span data-ttu-id="3648a-106">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3648a-106">Optional.</span></span> <span data-ttu-id="3648a-107">См. [список атрибутов](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="3648a-107">See [Attribute List](attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="3648a-108">Необязательно для одного из `Get` `Set` операторов и в этом свойстве.</span><span class="sxs-lookup"><span data-stu-id="3648a-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="3648a-109">Может применяться один из перечисленных ниже типов.</span><span class="sxs-lookup"><span data-stu-id="3648a-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="3648a-110">От</span><span class="sxs-lookup"><span data-stu-id="3648a-110">Protected</span></span>](../modifiers/protected.md)  
  
- [<span data-ttu-id="3648a-111">Friend</span><span class="sxs-lookup"><span data-stu-id="3648a-111">Friend</span></span>](../modifiers/friend.md)  
  
- [<span data-ttu-id="3648a-112">Частная</span><span class="sxs-lookup"><span data-stu-id="3648a-112">Private</span></span>](../modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="3648a-113">См. раздел [уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3648a-113">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="3648a-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3648a-114">Required.</span></span> <span data-ttu-id="3648a-115">Параметр, содержащий новое значение свойства.</span><span class="sxs-lookup"><span data-stu-id="3648a-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="3648a-116">Обязательный `Option Strict` , если имеет значение `On` .</span><span class="sxs-lookup"><span data-stu-id="3648a-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="3648a-117">Тип данных `value` параметра.</span><span class="sxs-lookup"><span data-stu-id="3648a-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="3648a-118">Указанный тип данных должен совпадать с типом данных свойства, в котором `Set` объявлен этот оператор.</span><span class="sxs-lookup"><span data-stu-id="3648a-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="3648a-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3648a-119">Optional.</span></span> <span data-ttu-id="3648a-120">Одна или несколько инструкций, выполняемых при `Set` вызове процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="3648a-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="3648a-121">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3648a-121">Required.</span></span> <span data-ttu-id="3648a-122">Завершает определение `Set` процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="3648a-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3648a-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="3648a-123">Remarks</span></span>  

 <span data-ttu-id="3648a-124">Каждое свойство должно иметь `Set` процедуру свойства, если только свойство не помечено как `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="3648a-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="3648a-125">`Set`Процедура используется для задания значения свойства.</span><span class="sxs-lookup"><span data-stu-id="3648a-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="3648a-126">Visual Basic автоматически вызывает процедуру свойства, `Set` когда оператор присваивания предоставляет значение, которое должно храниться в свойстве.</span><span class="sxs-lookup"><span data-stu-id="3648a-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="3648a-127">Visual Basic передает параметр в `Set` процедуру во время назначения свойств.</span><span class="sxs-lookup"><span data-stu-id="3648a-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="3648a-128">Если параметр для не указан `Set` , в интегрированной среде разработки (IDE) используется неявный параметр с именем `value` .</span><span class="sxs-lookup"><span data-stu-id="3648a-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="3648a-129">Параметр содержит значение, присваиваемое свойству.</span><span class="sxs-lookup"><span data-stu-id="3648a-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="3648a-130">Обычно это значение сохраняется в закрытой локальной переменной и возвращается при каждом `Get` вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="3648a-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="3648a-131">Текст объявления свойства может содержать только `Get` процедуры свойства и `Set` между [оператором Property](property-statement.md) и `End Property` оператором.</span><span class="sxs-lookup"><span data-stu-id="3648a-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="3648a-132">Он не может хранить ничего, Кроме этих процедур.</span><span class="sxs-lookup"><span data-stu-id="3648a-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="3648a-133">В частности, он не может хранить текущее значение свойства.</span><span class="sxs-lookup"><span data-stu-id="3648a-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="3648a-134">Это значение необходимо хранить за пределами свойства, так как при хранении в любой из процедур свойств другая процедура свойства не может получить к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="3648a-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="3648a-135">Обычным подходом является сохранение значения в [закрытой](../modifiers/private.md) переменной, объявленной на том же уровне, что и свойство.</span><span class="sxs-lookup"><span data-stu-id="3648a-135">The usual approach is to store the value in a [Private](../modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="3648a-136">Необходимо определить `Set` процедуру внутри свойства, к которому она применяется.</span><span class="sxs-lookup"><span data-stu-id="3648a-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="3648a-137">`Set`Процедура по умолчанию имеет уровень доступа содержащего его свойства, если только не используется `accessmodifier` в `Set` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3648a-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3648a-138">Правила</span><span class="sxs-lookup"><span data-stu-id="3648a-138">Rules</span></span>  
  
- <span data-ttu-id="3648a-139">**Уровни смешанного доступа.**</span><span class="sxs-lookup"><span data-stu-id="3648a-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="3648a-140">При определении свойства для чтения и записи можно дополнительно указать другой уровень доступа для `Get` `Set` процедуры или, но не для обоих.</span><span class="sxs-lookup"><span data-stu-id="3648a-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="3648a-141">В этом случае уровень доступа процедуры должен быть более четким, чем уровень доступа свойства.</span><span class="sxs-lookup"><span data-stu-id="3648a-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="3648a-142">Например, если свойство объявлено `Friend` , можно объявить `Set` процедуру `Private` , но не `Public` .</span><span class="sxs-lookup"><span data-stu-id="3648a-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="3648a-143">При определении `WriteOnly` свойства `Set` процедура представляет все свойство.</span><span class="sxs-lookup"><span data-stu-id="3648a-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="3648a-144">Нельзя объявить другой уровень доступа для `Set` , так как для свойства будет задано два уровня доступа.</span><span class="sxs-lookup"><span data-stu-id="3648a-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="3648a-145">Поведение</span><span class="sxs-lookup"><span data-stu-id="3648a-145">Behavior</span></span>  
  
- <span data-ttu-id="3648a-146">**Возврат из процедуры свойства.**</span><span class="sxs-lookup"><span data-stu-id="3648a-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="3648a-147">Когда `Set` процедура возвращается в вызывающий код, выполнение продолжится после оператора, который предоставил значение для сохранения.</span><span class="sxs-lookup"><span data-stu-id="3648a-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="3648a-148">`Set` процедуры свойств могут возвращать использование либо [оператора return](return-statement.md) , либо [оператора Exit](exit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3648a-148">`Set` property procedures can return using either the [Return Statement](return-statement.md) or the [Exit Statement](exit-statement.md).</span></span>  
  
     <span data-ttu-id="3648a-149">`Exit Property`Операторы и `Return` вызывают немедленный выход из процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="3648a-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="3648a-150">Любое количество `Exit Property` инструкций и `Return` может использоваться в любом месте процедуры, и можно смешивать `Exit Property` `Return` операторы и.</span><span class="sxs-lookup"><span data-stu-id="3648a-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3648a-151">Пример</span><span class="sxs-lookup"><span data-stu-id="3648a-151">Example</span></span>  

 <span data-ttu-id="3648a-152">В следующем примере инструкция используется `Set` для задания значения свойства.</span><span class="sxs-lookup"><span data-stu-id="3648a-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="3648a-153">См. также</span><span class="sxs-lookup"><span data-stu-id="3648a-153">See also</span></span>

- [<span data-ttu-id="3648a-154">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="3648a-154">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="3648a-155">Property Statement</span><span class="sxs-lookup"><span data-stu-id="3648a-155">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="3648a-156">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="3648a-156">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="3648a-157">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="3648a-157">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
