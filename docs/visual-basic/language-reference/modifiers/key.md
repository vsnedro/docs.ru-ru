---
title: Ключ
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 582ed5bb67b9c7504e736710aa4649cffb12ef45
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90868002"
---
# <a name="key-visual-basic"></a><span data-ttu-id="a213f-102">Key (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a213f-102">Key (Visual Basic)</span></span>

<span data-ttu-id="a213f-103">`Key`Ключевое слово позволяет задать поведение для свойств анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="a213f-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="a213f-104">Только свойства, указанные в качестве ключевых свойств, участвуют в тестах равенства между экземплярами анонимного типа или вычислении значений хэш-кода.</span><span class="sxs-lookup"><span data-stu-id="a213f-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="a213f-105">Значения ключевых свойств нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="a213f-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="a213f-106">Вы назначаете свойство анонимного типа в качестве ключевого свойства, помещая ключевое слово `Key` перед его объявлением в списке инициализации.</span><span class="sxs-lookup"><span data-stu-id="a213f-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="a213f-107">В следующем примере `Airline` и `FlightNo` являются ключевыми свойствами, но `Gate` не.</span><span class="sxs-lookup"><span data-stu-id="a213f-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 <span data-ttu-id="a213f-108">При создании нового анонимного типа он наследуется непосредственно от <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="a213f-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="a213f-109">Компилятор переопределяет три наследуемых члена: <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> и <xref:System.Object.ToString%2A> .</span><span class="sxs-lookup"><span data-stu-id="a213f-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="a213f-110">Код переопределения, созданный для <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> , основан на ключевых свойствах.</span><span class="sxs-lookup"><span data-stu-id="a213f-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="a213f-111">Значение, если в типе нет ключевых свойств <xref:System.Object.GetHashCode%2A> и <xref:System.Object.Equals%2A> они не переопределяются.</span><span class="sxs-lookup"><span data-stu-id="a213f-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="a213f-112">Равенство</span><span class="sxs-lookup"><span data-stu-id="a213f-112">Equality</span></span>  

 <span data-ttu-id="a213f-113">Два экземпляра анонимных типов равны, если они являются экземплярами одного типа и если значения их ключевых свойств равны.</span><span class="sxs-lookup"><span data-stu-id="a213f-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="a213f-114">В следующих примерах `flight2` значение равно `flight1` из предыдущего примера, так как они являются экземплярами одного и того же анонимного типа и имеют совпадающие значения для их ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="a213f-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="a213f-115">Однако `flight3` не равно, `flight1` поскольку имеет другое значение для ключевого свойства, `FlightNo` .</span><span class="sxs-lookup"><span data-stu-id="a213f-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="a213f-116">Тип экземпляра отличается `flight4` от типа, `flight1` так как он определяет различные свойства в качестве ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="a213f-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 <span data-ttu-id="a213f-117">Если два экземпляра объявляются только с неключевыми свойствами, идентичными в имени, типе, порядке и значении, два экземпляра не равны.</span><span class="sxs-lookup"><span data-stu-id="a213f-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="a213f-118">Экземпляр без ключевых свойств равен только самому себе.</span><span class="sxs-lookup"><span data-stu-id="a213f-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="a213f-119">Дополнительные сведения об условиях, при которых два экземпляра анонимных типов являются экземплярами одного и того же анонимного типа, см. в разделе [анонимные типы](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="a213f-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="a213f-120">Вычисление хэш-кода</span><span class="sxs-lookup"><span data-stu-id="a213f-120">Hash Code Calculation</span></span>  

 <span data-ttu-id="a213f-121">Например <xref:System.Object.Equals%2A> , хэш-функция, определенная в <xref:System.Object.GetHashCode%2A> для анонимного типа, основана на ключевых свойствах типа.</span><span class="sxs-lookup"><span data-stu-id="a213f-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="a213f-122">В следующих примерах показано взаимодействие между ключевыми свойствами и значениями хэш-кода.</span><span class="sxs-lookup"><span data-stu-id="a213f-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="a213f-123">Экземпляры анонимного типа, имеющие одинаковые значения для всех ключевых свойств, имеют одинаковое значение хэш-кода, даже если неключевые свойства не имеют совпадающих значений.</span><span class="sxs-lookup"><span data-stu-id="a213f-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="a213f-124">Следующая инструкция возвращает значение `True`.</span><span class="sxs-lookup"><span data-stu-id="a213f-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 <span data-ttu-id="a213f-125">Экземпляры анонимного типа, имеющие разные значения для одного или нескольких ключевых свойств, имеют разные значения хэш-кода.</span><span class="sxs-lookup"><span data-stu-id="a213f-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="a213f-126">Следующая инструкция возвращает значение `False`.</span><span class="sxs-lookup"><span data-stu-id="a213f-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 <span data-ttu-id="a213f-127">Экземпляры анонимных типов, которые обозначают различные свойства в качестве ключевых свойств, не являются экземплярами одного типа.</span><span class="sxs-lookup"><span data-stu-id="a213f-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="a213f-128">Они имеют разные значения хэш-кода, даже если имена и значения всех свойств одинаковы.</span><span class="sxs-lookup"><span data-stu-id="a213f-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="a213f-129">Следующая инструкция возвращает значение `False`.</span><span class="sxs-lookup"><span data-stu-id="a213f-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a><span data-ttu-id="a213f-130">Значения только для чтения</span><span class="sxs-lookup"><span data-stu-id="a213f-130">Read-Only Values</span></span>  

 <span data-ttu-id="a213f-131">Значения ключевых свойств нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="a213f-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="a213f-132">Например, в `flight1` предыдущих примерах `Airline` `FlightNo` поля и доступны только для чтения, но `Gate` могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="a213f-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="a213f-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a213f-133">See also</span></span>

- [<span data-ttu-id="a213f-134">Определение анонимного типа</span><span class="sxs-lookup"><span data-stu-id="a213f-134">Anonymous Type Definition</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [<span data-ttu-id="a213f-135">Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов</span><span class="sxs-lookup"><span data-stu-id="a213f-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="a213f-136">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="a213f-136">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
