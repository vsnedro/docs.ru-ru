---
title: Оператор TryCast
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: dc4807781f9e1aaf894016952911bd7b32c42948
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875315"
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="89189-102">Оператор TryCast (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89189-102">TryCast Operator (Visual Basic)</span></span>

<span data-ttu-id="89189-103">Вводит операцию преобразования типа, которая не создает исключение.</span><span class="sxs-lookup"><span data-stu-id="89189-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89189-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="89189-104">Remarks</span></span>  

 <span data-ttu-id="89189-105">Если попытка преобразования завершается неудачно `CType` и возникает `DirectCast` <xref:System.InvalidCastException> ошибка.</span><span class="sxs-lookup"><span data-stu-id="89189-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="89189-106">Это может негативно сказаться на производительности приложения.</span><span class="sxs-lookup"><span data-stu-id="89189-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="89189-107">`TryCast`[не возвращает ничего](../nothing.md), поэтому вместо того, чтобы выполнять обработку возможного исключения, необходимо только проверить возвращаемый результат для `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="89189-107">`TryCast` returns [Nothing](../nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="89189-108">`TryCast`Ключевое слово используется точно так же, как при использовании [функции CType](../functions/ctype-function.md) и ключевого слова [DirectCast operator](directcast-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="89189-108">You use the `TryCast` keyword the same way you use the [CType Function](../functions/ctype-function.md) and the [DirectCast Operator](directcast-operator.md) keyword.</span></span> <span data-ttu-id="89189-109">Укажите выражение в качестве первого аргумента и тип, чтобы преобразовать его в качестве второго аргумента.</span><span class="sxs-lookup"><span data-stu-id="89189-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="89189-110">`TryCast` работает только со ссылочными типами, такими как классы и интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="89189-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="89189-111">Для этого требуется отношение наследования или реализации между двумя типами.</span><span class="sxs-lookup"><span data-stu-id="89189-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="89189-112">Это означает, что один тип должен наследовать или реализовывать другой.</span><span class="sxs-lookup"><span data-stu-id="89189-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="89189-113">Ошибки и сбои</span><span class="sxs-lookup"><span data-stu-id="89189-113">Errors and Failures</span></span>  

 <span data-ttu-id="89189-114">`TryCast` выдает ошибку компилятора, если обнаруживается, что связь наследования или реализации не существует.</span><span class="sxs-lookup"><span data-stu-id="89189-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="89189-115">Но отсутствие ошибки компилятора не гарантирует успешного преобразования.</span><span class="sxs-lookup"><span data-stu-id="89189-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="89189-116">Если требуемое преобразование является узким, оно может привести к сбою во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="89189-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="89189-117">Если это происходит, `TryCast` возвращает [Nothing](../nothing.md).</span><span class="sxs-lookup"><span data-stu-id="89189-117">If this happens, `TryCast` returns [Nothing](../nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="89189-118">Ключевые слова преобразований</span><span class="sxs-lookup"><span data-stu-id="89189-118">Conversion Keywords</span></span>  

 <span data-ttu-id="89189-119">Ниже приведены сравнения ключевых слов преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="89189-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="89189-120">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="89189-120">Keyword</span></span>|<span data-ttu-id="89189-121">Типы данных</span><span class="sxs-lookup"><span data-stu-id="89189-121">Data types</span></span>|<span data-ttu-id="89189-122">Отношение аргумента</span><span class="sxs-lookup"><span data-stu-id="89189-122">Argument relationship</span></span>|<span data-ttu-id="89189-123">Сбой во время выполнения</span><span class="sxs-lookup"><span data-stu-id="89189-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="89189-124">CType Function</span><span class="sxs-lookup"><span data-stu-id="89189-124">CType Function</span></span>](../functions/ctype-function.md)|<span data-ttu-id="89189-125">Любые типы данных</span><span class="sxs-lookup"><span data-stu-id="89189-125">Any data types</span></span>|<span data-ttu-id="89189-126">Для двух типов данных должно быть определено расширяющее или суженное преобразование.</span><span class="sxs-lookup"><span data-stu-id="89189-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="89189-127">Создает <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="89189-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="89189-128">Оператор DirectCast</span><span class="sxs-lookup"><span data-stu-id="89189-128">DirectCast Operator</span></span>](directcast-operator.md)|<span data-ttu-id="89189-129">Любые типы данных</span><span class="sxs-lookup"><span data-stu-id="89189-129">Any data types</span></span>|<span data-ttu-id="89189-130">Один тип должен наследовать или реализовывать другой тип</span><span class="sxs-lookup"><span data-stu-id="89189-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="89189-131">Создает <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="89189-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="89189-132">Только ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="89189-132">Reference types only</span></span>|<span data-ttu-id="89189-133">Один тип должен наследовать или реализовывать другой тип</span><span class="sxs-lookup"><span data-stu-id="89189-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="89189-134">[Ничего не](../nothing.md) возвращает</span><span class="sxs-lookup"><span data-stu-id="89189-134">Returns [Nothing](../nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="89189-135">Пример</span><span class="sxs-lookup"><span data-stu-id="89189-135">Example</span></span>  

 <span data-ttu-id="89189-136">В следующем примере показано, как использовать `TryCast`.</span><span class="sxs-lookup"><span data-stu-id="89189-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="89189-137">См. также</span><span class="sxs-lookup"><span data-stu-id="89189-137">See also</span></span>

- [<span data-ttu-id="89189-138">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="89189-138">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="89189-139">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="89189-139">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
