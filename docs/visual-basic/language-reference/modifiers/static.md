---
title: Статические
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 3b323d5fb1c4f1357b9f476213793c69d29b7208
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402698"
---
# <a name="static-visual-basic"></a><span data-ttu-id="453a7-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="453a7-102">Static (Visual Basic)</span></span>
<span data-ttu-id="453a7-103">Указывает, что одна или несколько объявленных локальных переменных должны продолжать существовать и сохранить их последние значения после завершения процедуры, в которой они объявляются.</span><span class="sxs-lookup"><span data-stu-id="453a7-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="453a7-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="453a7-104">Remarks</span></span>  
 <span data-ttu-id="453a7-105">Как правило, локальная переменная в процедуре прекращает свое существование сразу после остановки процедуры.</span><span class="sxs-lookup"><span data-stu-id="453a7-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="453a7-106">Статическая переменная продолжает существовать и сохраняет ее Последнее значение.</span><span class="sxs-lookup"><span data-stu-id="453a7-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="453a7-107">В следующий раз, когда код вызывает процедуру, переменная не инициализируется повторно, и она по-прежнему содержит Последнее назначенное ей значение.</span><span class="sxs-lookup"><span data-stu-id="453a7-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="453a7-108">Статическая переменная будет существовать в течение времени существования класса или модуля, в котором он определен.</span><span class="sxs-lookup"><span data-stu-id="453a7-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="453a7-109">Правила</span><span class="sxs-lookup"><span data-stu-id="453a7-109">Rules</span></span>  
  
- <span data-ttu-id="453a7-110">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="453a7-110">**Declaration Context.**</span></span> <span data-ttu-id="453a7-111">Можно использовать `Static` только для локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="453a7-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="453a7-112">Это означает, что контекст объявления для `Static` переменной должен быть процедурой или блоком в процедуре и не может быть исходным файлом, пространством имен, классом, структурой или модулем.</span><span class="sxs-lookup"><span data-stu-id="453a7-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="453a7-113">Нельзя использовать `Static` внутри процедуры структуры.</span><span class="sxs-lookup"><span data-stu-id="453a7-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="453a7-114">Типы данных `Static` локальных переменных не могут быть определены.</span><span class="sxs-lookup"><span data-stu-id="453a7-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="453a7-115">Дополнительные сведения см. в разделе [определение локального типа](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="453a7-115">For more information, see [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="453a7-116">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="453a7-116">**Combined Modifiers.**</span></span> <span data-ttu-id="453a7-117">Нельзя указывать `Static` вместе с `ReadOnly` , `Shadows` или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="453a7-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="453a7-118">Поведение</span><span class="sxs-lookup"><span data-stu-id="453a7-118">Behavior</span></span>  
 <span data-ttu-id="453a7-119">При объявлении статической переменной в `Shared` процедуре для всего приложения доступна только одна копия статической переменной.</span><span class="sxs-lookup"><span data-stu-id="453a7-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="453a7-120">Процедура вызывается с `Shared` помощью имени класса, а не переменной, указывающей на экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="453a7-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="453a7-121">При объявлении статической переменной в процедуре, которая не `Shared` имеет, для каждого экземпляра класса доступна только одна копия переменной.</span><span class="sxs-lookup"><span data-stu-id="453a7-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="453a7-122">Для вызова процедуры, которая не является общей, используется переменная, указывающая на конкретный экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="453a7-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="453a7-123">Пример</span><span class="sxs-lookup"><span data-stu-id="453a7-123">Example</span></span>  
 <span data-ttu-id="453a7-124">В следующем примере показано использование функции `Static`.</span><span class="sxs-lookup"><span data-stu-id="453a7-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="453a7-125">`Static`Переменная `totalSales` инициализируется значением 0 только один раз.</span><span class="sxs-lookup"><span data-stu-id="453a7-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="453a7-126">При каждом вводе `updateSales` `totalSales` по-прежнему будет присвоено самое последнее значение, вычисленное для него.</span><span class="sxs-lookup"><span data-stu-id="453a7-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="453a7-127">`Static`Модификатор можно использовать в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="453a7-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="453a7-128">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="453a7-128">Dim Statement</span></span>](../statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="453a7-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="453a7-129">See also</span></span>

- [<span data-ttu-id="453a7-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="453a7-130">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="453a7-131">Общий</span><span class="sxs-lookup"><span data-stu-id="453a7-131">Shared</span></span>](shared.md)
- [<span data-ttu-id="453a7-132">Время существования в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="453a7-132">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="453a7-133">Объявление переменной</span><span class="sxs-lookup"><span data-stu-id="453a7-133">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="453a7-134">Структуры</span><span class="sxs-lookup"><span data-stu-id="453a7-134">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="453a7-135">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="453a7-135">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="453a7-136">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="453a7-136">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
