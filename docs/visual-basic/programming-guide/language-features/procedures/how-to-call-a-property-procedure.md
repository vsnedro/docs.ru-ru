---
title: Практическое руководство. Вызов процедуры свойства
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 0b35751136937d4cee5b3ca9669b43d3fbdf71a1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071957"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="fa239-102">Практическое руководство. Вызов процедуры свойства (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa239-102">How to: Call a Property Procedure (Visual Basic)</span></span>

<span data-ttu-id="fa239-103">Процедура свойства вызывается путем сохранения значения в свойстве или извлечения его значения.</span><span class="sxs-lookup"><span data-stu-id="fa239-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="fa239-104">Доступ к свойству осуществляется так же, как и к переменной.</span><span class="sxs-lookup"><span data-stu-id="fa239-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="fa239-105">`Set`Процедура свойства сохраняет значение, и его `Get` процедура получает значение.</span><span class="sxs-lookup"><span data-stu-id="fa239-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="fa239-106">Однако эти процедуры не вызываются явным образом по имени.</span><span class="sxs-lookup"><span data-stu-id="fa239-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="fa239-107">Свойство используется в операторе присваивания или в выражении так же, как и при хранении или извлечении значения переменной.</span><span class="sxs-lookup"><span data-stu-id="fa239-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="fa239-108">Visual Basic выполняет вызовы процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="fa239-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="fa239-109">Вызов процедуры Get свойства</span><span class="sxs-lookup"><span data-stu-id="fa239-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="fa239-110">Используйте имя свойства в выражении так же, как при использовании имени переменной.</span><span class="sxs-lookup"><span data-stu-id="fa239-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="fa239-111">Свойство можно использовать в любом месте, где можно использовать переменную или константу.</span><span class="sxs-lookup"><span data-stu-id="fa239-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="fa239-112">-или-</span><span class="sxs-lookup"><span data-stu-id="fa239-112">-or-</span></span>  
  
     <span data-ttu-id="fa239-113">Используйте имя свойства после знака равенства ( `=` ) в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="fa239-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="fa239-114">В следующем примере считывается значение <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> свойства, неявно вызывающего его `Get` процедуру.</span><span class="sxs-lookup"><span data-stu-id="fa239-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="fa239-115">Если свойство принимает аргументы, следует следовать имени свойства с круглыми скобками, чтобы заключить список аргументов.</span><span class="sxs-lookup"><span data-stu-id="fa239-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="fa239-116">Если аргументы отсутствуют, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="fa239-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="fa239-117">Поместите аргументы в список аргументов в круглых скобках, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="fa239-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="fa239-118">Убедитесь, что аргументы указываются в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="fa239-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="fa239-119">Значение свойства участвует в выражении точно так же, как переменная или константа, либо хранится в переменной или свойстве в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="fa239-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="fa239-120">Вызов процедуры Set свойства</span><span class="sxs-lookup"><span data-stu-id="fa239-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="fa239-121">Используйте имя свойства в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="fa239-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="fa239-122">В следующем примере задается значение <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> свойства, которое неявно вызывает `Set` процедуру.</span><span class="sxs-lookup"><span data-stu-id="fa239-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="fa239-123">Если свойство принимает аргументы, следует следовать имени свойства с круглыми скобками, чтобы заключить список аргументов.</span><span class="sxs-lookup"><span data-stu-id="fa239-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="fa239-124">Если аргументы отсутствуют, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="fa239-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="fa239-125">Поместите аргументы в список аргументов в круглых скобках, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="fa239-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="fa239-126">Убедитесь, что аргументы указываются в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="fa239-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="fa239-127">Значение, созданное в правой части оператора присваивания, хранится в свойстве.</span><span class="sxs-lookup"><span data-stu-id="fa239-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa239-128">См. также</span><span class="sxs-lookup"><span data-stu-id="fa239-128">See also</span></span>

- [<span data-ttu-id="fa239-129">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="fa239-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="fa239-130">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="fa239-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fa239-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="fa239-131">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="fa239-132">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa239-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="fa239-133">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="fa239-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="fa239-134">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="fa239-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="fa239-135">Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa239-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="fa239-136">Практическое руководство. Запись значения в свойство</span><span class="sxs-lookup"><span data-stu-id="fa239-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="fa239-137">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="fa239-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="fa239-138">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="fa239-138">Get Statement</span></span>](../../../language-reference/statements/get-statement.md)
- [<span data-ttu-id="fa239-139">Инструкция SET</span><span class="sxs-lookup"><span data-stu-id="fa239-139">Set Statement</span></span>](../../../language-reference/statements/set-statement.md)
