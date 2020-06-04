---
title: 'Инициализаторы объектов: именованные и анонимные типы'
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: 5561812a53e2fe45c3ad4d12d0e18a8a1e948559
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411770"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a><span data-ttu-id="af49d-102">Инициализаторы объектов: именованные и анонимные типы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af49d-102">Object Initializers: Named and Anonymous Types (Visual Basic)</span></span>
<span data-ttu-id="af49d-103">Инициализаторы объектов позволяют задавать свойства для сложного объекта с помощью одного выражения.</span><span class="sxs-lookup"><span data-stu-id="af49d-103">Object initializers enable you to specify properties for a complex object by using a single expression.</span></span> <span data-ttu-id="af49d-104">Они могут использоваться для создания экземпляров именованных типов и анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="af49d-104">They can be used to create instances of named types and of anonymous types.</span></span>  
  
## <a name="declarations"></a><span data-ttu-id="af49d-105">Объявления</span><span class="sxs-lookup"><span data-stu-id="af49d-105">Declarations</span></span>  
 <span data-ttu-id="af49d-106">Объявления экземпляров именованных и анонимных типов могут выглядеть почти одинаково, но их последствия не совпадают.</span><span class="sxs-lookup"><span data-stu-id="af49d-106">Declarations of instances of named and anonymous types can look almost identical, but their effects are not the same.</span></span> <span data-ttu-id="af49d-107">Каждая категория имеет свои возможности и ограничения.</span><span class="sxs-lookup"><span data-stu-id="af49d-107">Each category has abilities and restrictions of its own.</span></span> <span data-ttu-id="af49d-108">В следующем примере показан удобный способ объявления и инициализации экземпляра именованного класса с `Customer` помощью списка инициализаторов объектов.</span><span class="sxs-lookup"><span data-stu-id="af49d-108">The following example shows a convenient way to declare and initialize an instance of a named class, `Customer`, by using an object initializer list.</span></span> <span data-ttu-id="af49d-109">Обратите внимание, что имя класса указывается после ключевого слова `New` .</span><span class="sxs-lookup"><span data-stu-id="af49d-109">Notice that the name of the class is specified after the keyword `New`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#1)]  
  
 <span data-ttu-id="af49d-110">Анонимный тип не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="af49d-110">An anonymous type has no usable name.</span></span> <span data-ttu-id="af49d-111">Поэтому создание экземпляра анонимного типа не может включать имя класса.</span><span class="sxs-lookup"><span data-stu-id="af49d-111">Therefore an instantiation of an anonymous type cannot include a class name.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
 <span data-ttu-id="af49d-112">Требования и результаты двух объявлений не совпадают.</span><span class="sxs-lookup"><span data-stu-id="af49d-112">The requirements and results of the two declarations are not the same.</span></span> <span data-ttu-id="af49d-113">Для `namedCust` класс, `Customer` имеющий свойство, `Name` должен уже существовать, а объявление создает экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="af49d-113">For `namedCust`, a `Customer` class that has a `Name` property must already exist, and the declaration creates an instance of that class.</span></span> <span data-ttu-id="af49d-114">Для `anonymousCust` компилятор определяет новый класс, который имеет одно свойство, строку с именем `Name` и создает новый экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="af49d-114">For `anonymousCust`, the compiler defines a new class that has one property, a string called `Name`, and creates a new instance of that class.</span></span>  
  
## <a name="named-types"></a><span data-ttu-id="af49d-115">Именованные типы</span><span class="sxs-lookup"><span data-stu-id="af49d-115">Named Types</span></span>  
 <span data-ttu-id="af49d-116">Инициализаторы объектов предоставляют простой способ вызова конструктора типа, а затем задают значения некоторых или всех свойств в одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="af49d-116">Object initializers provide a simple way to call the constructor of a type and then set the values of some or all properties in a single statement.</span></span> <span data-ttu-id="af49d-117">Компилятор вызывает соответствующий конструктор для инструкции: конструктор без параметров, если аргументы не представлены, или параметризованный конструктор при отправке одного или нескольких аргументов.</span><span class="sxs-lookup"><span data-stu-id="af49d-117">The compiler invokes the appropriate constructor for the statement: the parameterless constructor if no arguments are presented, or a parameterized constructor if one or more arguments are sent.</span></span> <span data-ttu-id="af49d-118">После этого заданные свойства инициализируются в том порядке, в котором они представлены в списке инициализаторов.</span><span class="sxs-lookup"><span data-stu-id="af49d-118">After that, the specified properties are initialized in the order in which they are presented in the initializer list.</span></span>  
  
 <span data-ttu-id="af49d-119">Каждая инициализация в списке инициализаторов состоит из присваивания начального значения члену класса.</span><span class="sxs-lookup"><span data-stu-id="af49d-119">Each initialization in the initializer list consists of the assignment of an initial value to a member of the class.</span></span> <span data-ttu-id="af49d-120">Имена и типы данных элементов определяются при определении класса.</span><span class="sxs-lookup"><span data-stu-id="af49d-120">The names and data types of the members are determined when the class is defined.</span></span> <span data-ttu-id="af49d-121">В следующих примерах `Customer` класс должен существовать и должен иметь члены с именем `Name` и `City` , которые могут принимать строковые значения.</span><span class="sxs-lookup"><span data-stu-id="af49d-121">In the following examples, the `Customer` class must exist, and must have members named `Name` and `City` that can accept string values.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#3)]  
  
 <span data-ttu-id="af49d-122">Кроме того, можно получить тот же результат, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="af49d-122">Alternatively, you can obtain the same result by using the following code:</span></span>  
  
 [!code-vb[VbVbalrObjectInit#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#4)]  
  
 <span data-ttu-id="af49d-123">Каждое из этих объявлений эквивалентно следующему примеру, который создает `Customer` объект с помощью конструктора без параметров, а затем задает начальные значения для `Name` свойств и с `City` помощью `With` инструкции.</span><span class="sxs-lookup"><span data-stu-id="af49d-123">Each of these declarations is equivalent to the following example, which creates a `Customer` object by using the parameterless constructor, and then specifies initial values for the `Name` and `City` properties by using a `With` statement.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#5)]  
  
 <span data-ttu-id="af49d-124">Если `Customer` класс содержит параметризованный конструктор, который позволяет отправить значение для `Name` , например, можно также объявить и инициализировать `Customer` объект следующими способами.</span><span class="sxs-lookup"><span data-stu-id="af49d-124">If the `Customer` class contains a parameterized constructor that enables you to send in a value for `Name`, for example, you can also declare and initialize a `Customer` object in the following ways:</span></span>  
  
 [!code-vb[VbVbalrObjectInit#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#6)]  
  
 <span data-ttu-id="af49d-125">Не нужно инициализировать все свойства, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="af49d-125">You do not have to initialize all properties, as the following code shows.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#7)]  
  
 <span data-ttu-id="af49d-126">Однако список инициализации не может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="af49d-126">However, the initialization list cannot be empty.</span></span> <span data-ttu-id="af49d-127">Неинициализированные свойства сохраняют значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="af49d-127">Uninitialized properties retain their default values.</span></span>  
  
### <a name="type-inference-with-named-types"></a><span data-ttu-id="af49d-128">Вывод типа с именованными типами</span><span class="sxs-lookup"><span data-stu-id="af49d-128">Type Inference with Named Types</span></span>  
 <span data-ttu-id="af49d-129">Код для объявления можно сократить `cust1` , объединив инициализаторы объектов и вывод локального типа.</span><span class="sxs-lookup"><span data-stu-id="af49d-129">You can shorten the code for the declaration of `cust1` by combining object initializers and local type inference.</span></span> <span data-ttu-id="af49d-130">Это позволяет опустить `As` предложение в объявлении переменной.</span><span class="sxs-lookup"><span data-stu-id="af49d-130">This enables you to omit the `As` clause in the variable declaration.</span></span> <span data-ttu-id="af49d-131">Тип данных переменной выводится из типа объекта, созданного назначением.</span><span class="sxs-lookup"><span data-stu-id="af49d-131">The data type of the variable is inferred from the type of the object that is created by the assignment.</span></span> <span data-ttu-id="af49d-132">В следующем примере типом `cust6` является `Customer` .</span><span class="sxs-lookup"><span data-stu-id="af49d-132">In the following example, the type of `cust6` is `Customer`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#8)]  
  
### <a name="remarks-about-named-types"></a><span data-ttu-id="af49d-133">Примечания об именованных типах</span><span class="sxs-lookup"><span data-stu-id="af49d-133">Remarks About Named Types</span></span>  
  
- <span data-ttu-id="af49d-134">Член класса не может быть инициализирован более одного раза в списке инициализаторов объектов.</span><span class="sxs-lookup"><span data-stu-id="af49d-134">A class member cannot be initialized more than one time in the object initializer list.</span></span> <span data-ttu-id="af49d-135">Объявление `cust7` вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="af49d-135">The declaration of `cust7` causes an error.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#9)]  
  
- <span data-ttu-id="af49d-136">Элемент может использоваться для инициализации самого себя или другого поля.</span><span class="sxs-lookup"><span data-stu-id="af49d-136">A member can be used to initialize itself or another field.</span></span> <span data-ttu-id="af49d-137">Если доступ к элементу осуществляется до инициализации, как показано в следующем объявлении для `cust8` , будет использоваться значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="af49d-137">If a member is accessed before it has been initialized, as in the following declaration for `cust8`, the default value will be used.</span></span> <span data-ttu-id="af49d-138">Помните, что при обработке объявления, использующего инициализатор объекта, первое, что происходит, это то, что вызывается соответствующий конструктор.</span><span class="sxs-lookup"><span data-stu-id="af49d-138">Remember that when a declaration that uses an object initializer is processed, the first thing that happens is that the appropriate constructor is invoked.</span></span> <span data-ttu-id="af49d-139">После этого инициализируются отдельные поля в списке инициализаторов.</span><span class="sxs-lookup"><span data-stu-id="af49d-139">After that, the individual fields in the initializer list are initialized.</span></span> <span data-ttu-id="af49d-140">В следующих примерах значение по умолчанию для присваивается `Name` `cust8` , а инициализированное значение присваивается в `cust9` .</span><span class="sxs-lookup"><span data-stu-id="af49d-140">In the following examples, the default value for `Name` is assigned for `cust8`, and an initialized value is assigned in `cust9`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#10)]  
  
     <span data-ttu-id="af49d-141">В следующем примере параметризованный конструктор используется из `cust3` и `cust4` для объявления и инициализации и `cust10` `cust11` .</span><span class="sxs-lookup"><span data-stu-id="af49d-141">The following example uses the parameterized constructor from `cust3` and `cust4` to declare and initialize `cust10` and `cust11`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#11)]  
  
- <span data-ttu-id="af49d-142">Инициализаторы объектов могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="af49d-142">Object initializers can be nested.</span></span> <span data-ttu-id="af49d-143">В следующем примере класс имеет `AddressClass` два свойства: `City` и `State` , и `Customer` класс имеет `Address` свойство, которое является экземпляром `AddressClass` .</span><span class="sxs-lookup"><span data-stu-id="af49d-143">In the following example, `AddressClass` is a class that has two properties, `City` and `State`, and the `Customer` class has an `Address` property that is an instance of `AddressClass`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#12)]  
  
- <span data-ttu-id="af49d-144">Список инициализации не может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="af49d-144">The initialization list cannot be empty.</span></span>  
  
- <span data-ttu-id="af49d-145">Инициализируемый экземпляр не может иметь тип Object.</span><span class="sxs-lookup"><span data-stu-id="af49d-145">The instance being initialized cannot be of type Object.</span></span>  
  
- <span data-ttu-id="af49d-146">Инициализируемые члены класса не могут быть общими членами, членами только для чтения, константами или вызовами методов.</span><span class="sxs-lookup"><span data-stu-id="af49d-146">Class members being initialized cannot be shared members, read-only members, constants, or method calls.</span></span>  
  
- <span data-ttu-id="af49d-147">Инициализируемые члены класса не могут индексироваться или уточняться.</span><span class="sxs-lookup"><span data-stu-id="af49d-147">Class members being initialized cannot be indexed or qualified.</span></span> <span data-ttu-id="af49d-148">В следующих примерах вызываются ошибки компилятора:</span><span class="sxs-lookup"><span data-stu-id="af49d-148">The following examples raise compiler errors:</span></span>  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a><span data-ttu-id="af49d-149">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="af49d-149">Anonymous Types</span></span>  
 <span data-ttu-id="af49d-150">Анонимные типы используют инициализаторы объектов для создания экземпляров новых типов, которые явно не определены и не имеют имени.</span><span class="sxs-lookup"><span data-stu-id="af49d-150">Anonymous types use object initializers to create instances of new types that you do not explicitly define and name.</span></span> <span data-ttu-id="af49d-151">Вместо этого компилятор создает тип в соответствии со свойствами, которые вы указываете в списке инициализатора объекта.</span><span class="sxs-lookup"><span data-stu-id="af49d-151">Instead, the compiler generates a type according to the properties you designate in the object initializer list.</span></span> <span data-ttu-id="af49d-152">Так как имя типа не указано, оно называется *анонимным типом*.</span><span class="sxs-lookup"><span data-stu-id="af49d-152">Because the name of the type is not specified, it is referred to as an *anonymous type*.</span></span> <span data-ttu-id="af49d-153">Например, Сравните следующее объявление с предыдущим для `cust6` .</span><span class="sxs-lookup"><span data-stu-id="af49d-153">For example, compare the following declaration to the earlier one for `cust6`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#13)]  
  
 <span data-ttu-id="af49d-154">Единственное отличие состоит в том, что после `New` для типа данных не указано имя.</span><span class="sxs-lookup"><span data-stu-id="af49d-154">The only difference syntactically is that no name is specified after `New` for the data type.</span></span> <span data-ttu-id="af49d-155">Тем не менее, что происходит совершенно иначе.</span><span class="sxs-lookup"><span data-stu-id="af49d-155">However, what happens is quite different.</span></span> <span data-ttu-id="af49d-156">Компилятор определяет новый анонимный тип, который имеет два свойства: `Name` и и `City` создает экземпляр с указанными значениями.</span><span class="sxs-lookup"><span data-stu-id="af49d-156">The compiler defines a new anonymous type that has two properties, `Name` and `City`, and creates an instance of it with the specified values.</span></span> <span data-ttu-id="af49d-157">Определение типа определяет типы `Name` и `City` в примере как строки.</span><span class="sxs-lookup"><span data-stu-id="af49d-157">Type inference determines the types of `Name` and `City` in the example to be strings.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="af49d-158">Имя анонимного типа создается компилятором и может отличаться от компиляции к компиляции.</span><span class="sxs-lookup"><span data-stu-id="af49d-158">The name of the anonymous type is generated by the compiler, and may vary from compilation to compilation.</span></span> <span data-ttu-id="af49d-159">Код не должен использовать имя анонимного типа или полагаться на него.</span><span class="sxs-lookup"><span data-stu-id="af49d-159">Your code should not use or rely on the name of an anonymous type.</span></span>  
  
 <span data-ttu-id="af49d-160">Поскольку имя типа недоступно, нельзя использовать `As` предложение для объявления `cust13` .</span><span class="sxs-lookup"><span data-stu-id="af49d-160">Because the name of the type is not available, you cannot use an `As` clause to declare `cust13`.</span></span> <span data-ttu-id="af49d-161">Его тип должен быть определен.</span><span class="sxs-lookup"><span data-stu-id="af49d-161">Its type must be inferred.</span></span> <span data-ttu-id="af49d-162">Без использования позднего связывания это ограничивает использование анонимных типов локальными переменными.</span><span class="sxs-lookup"><span data-stu-id="af49d-162">Without using late binding, this limits the use of anonymous types to local variables.</span></span>  
  
 <span data-ttu-id="af49d-163">Анонимные типы обеспечивают важную поддержку запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="af49d-163">Anonymous types provide critical support for LINQ queries.</span></span> <span data-ttu-id="af49d-164">Дополнительные сведения об использовании анонимных типов в запросах см. в разделе [анонимные типы](anonymous-types.md) и [Введение в LINQ в Visual Basic](../linq/introduction-to-linq.md).</span><span class="sxs-lookup"><span data-stu-id="af49d-164">For more information about the use of anonymous types in queries, see [Anonymous Types](anonymous-types.md) and [Introduction to LINQ in Visual Basic](../linq/introduction-to-linq.md).</span></span>  
  
### <a name="remarks-about-anonymous-types"></a><span data-ttu-id="af49d-165">Примечания о анонимных типах</span><span class="sxs-lookup"><span data-stu-id="af49d-165">Remarks About Anonymous Types</span></span>  
  
- <span data-ttu-id="af49d-166">Как правило, все или большинство свойств в объявлении анонимного типа будут ключевыми свойствами, которые указываются путем ввода ключевого слова `Key` перед именем свойства.</span><span class="sxs-lookup"><span data-stu-id="af49d-166">Typically, all or most of the properties in an anonymous type declaration will be key properties, which are indicated by typing the keyword `Key` in front of the property name.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#14)]  
  
     <span data-ttu-id="af49d-167">Дополнительные сведения о ключевых свойствах см. в разделе [Key](../../../language-reference/modifiers/key.md).</span><span class="sxs-lookup"><span data-stu-id="af49d-167">For more information about key properties, see [Key](../../../language-reference/modifiers/key.md).</span></span>  
  
- <span data-ttu-id="af49d-168">Как и именованные типы, списки инициализаторов для определений анонимных типов должны объявлять хотя бы одно свойство.</span><span class="sxs-lookup"><span data-stu-id="af49d-168">Like named types, initializer lists for anonymous type definitions must declare at least one property.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
- <span data-ttu-id="af49d-169">При объявлении экземпляра анонимного типа компилятор создает соответствующее определение анонимного типа.</span><span class="sxs-lookup"><span data-stu-id="af49d-169">When an instance of an anonymous type is declared, the compiler generates a matching anonymous type definition.</span></span> <span data-ttu-id="af49d-170">Имена и типы данных свойств берутся из объявления экземпляра и включаются компилятором в определение.</span><span class="sxs-lookup"><span data-stu-id="af49d-170">The names and data types of the properties are taken from the instance declaration, and are included by the compiler in the definition.</span></span> <span data-ttu-id="af49d-171">Свойства не именуются и не определяются заранее, так как они бы были для именованного типа.</span><span class="sxs-lookup"><span data-stu-id="af49d-171">The properties are not named and defined in advance, as they would be for a named type.</span></span> <span data-ttu-id="af49d-172">Их типы выводятся.</span><span class="sxs-lookup"><span data-stu-id="af49d-172">Their types are inferred.</span></span> <span data-ttu-id="af49d-173">Нельзя указать типы данных свойств с помощью `As` предложения.</span><span class="sxs-lookup"><span data-stu-id="af49d-173">You cannot specify the data types of the properties by using an `As` clause.</span></span>  
  
- <span data-ttu-id="af49d-174">Анонимные типы также могут устанавливать имена и значения их свойств несколькими другими способами.</span><span class="sxs-lookup"><span data-stu-id="af49d-174">Anonymous types can also establish the names and values of their properties in several other ways.</span></span> <span data-ttu-id="af49d-175">Например, свойство анонимного типа может принимать как имя, так и значение переменной, а также имя и значение свойства другого объекта.</span><span class="sxs-lookup"><span data-stu-id="af49d-175">For example, an anonymous type property can take both the name and the value of a variable, or the name and value of a property of another object.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#15)]  
  
     <span data-ttu-id="af49d-176">Дополнительные сведения о параметрах определения свойств в анонимных типах см. [в разделе как вывести имена и типы свойств в объявлениях анонимного типа](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span><span class="sxs-lookup"><span data-stu-id="af49d-176">For more information about the options for defining properties in anonymous types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af49d-177">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="af49d-177">See also</span></span>

- [<span data-ttu-id="af49d-178">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="af49d-178">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="af49d-179">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="af49d-179">Anonymous Types</span></span>](anonymous-types.md)
- <span data-ttu-id="af49d-180">[Introduction to LINQ in Visual Basic](../linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af49d-180">[Introduction to LINQ in Visual Basic](../linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="af49d-181">Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов</span><span class="sxs-lookup"><span data-stu-id="af49d-181">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [<span data-ttu-id="af49d-182">Клавиша</span><span class="sxs-lookup"><span data-stu-id="af49d-182">Key</span></span>](../../../language-reference/modifiers/key.md)
- [<span data-ttu-id="af49d-183">Практическое руководство. Объявление объекта с помощью инициализатора объектов</span><span class="sxs-lookup"><span data-stu-id="af49d-183">How to: Declare an Object by Using an Object Initializer</span></span>](how-to-declare-an-object-by-using-an-object-initializer.md)
