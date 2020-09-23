---
title: Разделяемые методы
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: 0e7c1315df50e83c919270f76405e80862bdd03b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071265"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="231d5-102">Разделяемые методы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="231d5-102">Partial Methods (Visual Basic)</span></span>

<span data-ttu-id="231d5-103">Разделяемые методы позволяют разработчикам вставлять в код пользовательскую логику.</span><span class="sxs-lookup"><span data-stu-id="231d5-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="231d5-104">Как правило, код является частью класса, созданного конструктором.</span><span class="sxs-lookup"><span data-stu-id="231d5-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="231d5-105">Разделяемые методы определяются в разделяемом классе, созданном генератором кода, и обычно используются для предоставления уведомлений о том, что что-то изменилось.</span><span class="sxs-lookup"><span data-stu-id="231d5-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="231d5-106">Они позволяют разработчику указать пользовательское поведение в ответ на изменение.</span><span class="sxs-lookup"><span data-stu-id="231d5-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="231d5-107">Конструктор генератора кода определяет только сигнатуру метода и один или несколько вызовов метода.</span><span class="sxs-lookup"><span data-stu-id="231d5-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="231d5-108">Разработчики могут предоставлять реализации для метода, если им нужно настроить поведение созданного кода.</span><span class="sxs-lookup"><span data-stu-id="231d5-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="231d5-109">Если реализация не предоставлена, то вызовы метода удаляются компилятором, что приводит к дополнительной нагрузке на производительность.</span><span class="sxs-lookup"><span data-stu-id="231d5-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="231d5-110">Объявление</span><span class="sxs-lookup"><span data-stu-id="231d5-110">Declaration</span></span>  

 <span data-ttu-id="231d5-111">Созданный код помечает определение разделяемого метода, помещая ключевое слово `Partial` в начале строки подписи.</span><span class="sxs-lookup"><span data-stu-id="231d5-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="231d5-112">Определение должно соответствовать следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="231d5-112">The definition must meet the following conditions:</span></span>  
  
- <span data-ttu-id="231d5-113">Метод должен быть, а `Sub` не `Function` .</span><span class="sxs-lookup"><span data-stu-id="231d5-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
- <span data-ttu-id="231d5-114">Тело метода должно оставаться пустым.</span><span class="sxs-lookup"><span data-stu-id="231d5-114">The body of the method must be left empty.</span></span>  
  
- <span data-ttu-id="231d5-115">Модификатор доступа должен иметь значение `Private` .</span><span class="sxs-lookup"><span data-stu-id="231d5-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="231d5-116">Реализация</span><span class="sxs-lookup"><span data-stu-id="231d5-116">Implementation</span></span>  

 <span data-ttu-id="231d5-117">Реализация состоит в основном за заполнением тела разделяемого метода.</span><span class="sxs-lookup"><span data-stu-id="231d5-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="231d5-118">Реализация обычно находится в отдельном разделяемом классе из определения и написана разработчиком, желающим расширить созданный код.</span><span class="sxs-lookup"><span data-stu-id="231d5-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="231d5-119">В предыдущем примере сигнатура дублируется в объявлении точно, но возможны вариации.</span><span class="sxs-lookup"><span data-stu-id="231d5-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="231d5-120">В частности, можно добавить другие модификаторы, например `Overloads` или `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="231d5-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="231d5-121">Допускается только один `Overrides` модификатор.</span><span class="sxs-lookup"><span data-stu-id="231d5-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="231d5-122">Дополнительные сведения об модификаторах методов см. в разделе [оператор подраздела](../../../language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="231d5-122">For more information about method modifiers, see [Sub Statement](../../../language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="231d5-123">Использовать</span><span class="sxs-lookup"><span data-stu-id="231d5-123">Use</span></span>  

 <span data-ttu-id="231d5-124">Разделяемый метод вызывается так же, как и любая другая `Sub` процедура.</span><span class="sxs-lookup"><span data-stu-id="231d5-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="231d5-125">Если метод реализован, вычисляются аргументы и выполняется тело метода.</span><span class="sxs-lookup"><span data-stu-id="231d5-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="231d5-126">Однако помните, что реализация разделяемого метода является необязательной.</span><span class="sxs-lookup"><span data-stu-id="231d5-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="231d5-127">Если метод не реализован, вызов этого метода не имеет результата, и выражения, передаваемые в качестве аргументов в метод, не оцениваются.</span><span class="sxs-lookup"><span data-stu-id="231d5-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="231d5-128">Пример</span><span class="sxs-lookup"><span data-stu-id="231d5-128">Example</span></span>  

 <span data-ttu-id="231d5-129">В файле Product. Designer. vb Определите `Product` класс, имеющий `Quantity` свойство.</span><span class="sxs-lookup"><span data-stu-id="231d5-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 <span data-ttu-id="231d5-130">В файле Product. vb укажите реализацию для `QuantityChanged` .</span><span class="sxs-lookup"><span data-stu-id="231d5-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 <span data-ttu-id="231d5-131">Наконец, в методе Main проекта объявите `Product` экземпляр и укажите начальное значение для его `Quantity` Свойства.</span><span class="sxs-lookup"><span data-stu-id="231d5-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 <span data-ttu-id="231d5-132">Появится окно сообщения, в котором отображается следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="231d5-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="231d5-133">См. также</span><span class="sxs-lookup"><span data-stu-id="231d5-133">See also</span></span>

- [<span data-ttu-id="231d5-134">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="231d5-134">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="231d5-135">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="231d5-135">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="231d5-136">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="231d5-136">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="231d5-137">Partial</span><span class="sxs-lookup"><span data-stu-id="231d5-137">Partial</span></span>](../../../language-reference/modifiers/partial.md)
- [<span data-ttu-id="231d5-138">Создание кода в LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="231d5-138">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="231d5-139">Добавление бизнес-логики с использованием разделяемых методов</span><span class="sxs-lookup"><span data-stu-id="231d5-139">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
