---
title: Практическое руководство. Объявление структуры
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: a6b70d0973e92db90e35e61b7fed2279c5b0bac3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393978"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="fcb49-102">Практическое руководство. Объявление структуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fcb49-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="fcb49-103">Объявление структуры начинается с [оператора Structure](../../../language-reference/statements/structure-statement.md)и заканчивается `End Structure` инструкцией.</span><span class="sxs-lookup"><span data-stu-id="fcb49-103">You begin a structure declaration with the [Structure Statement](../../../language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="fcb49-104">Между этими двумя операторами необходимо объявить хотя бы один *элемент*.</span><span class="sxs-lookup"><span data-stu-id="fcb49-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="fcb49-105">Элементы могут иметь любой тип данных, но хотя бы один из них должен быть либо необщей переменной, либо нестандартным, ненастраиваемым событием.</span><span class="sxs-lookup"><span data-stu-id="fcb49-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="fcb49-106">Нельзя инициализировать какие либо элементы структуры в объявлении структуры.</span><span class="sxs-lookup"><span data-stu-id="fcb49-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="fcb49-107">При объявлении переменной, имеющей тип структуры, необходимо назначить значения элементам, обращаясь к ним через переменную.</span><span class="sxs-lookup"><span data-stu-id="fcb49-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="fcb49-108">Обсуждение различий между структурами и классами см. в разделе [структуры и классы](structures-and-classes.md).</span><span class="sxs-lookup"><span data-stu-id="fcb49-108">For a discussion of the differences between structures and classes, see [Structures and Classes](structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="fcb49-109">В демонстрационных целях рассмотрим ситуацию, когда необходимо отследить имя сотрудника, телефонное расширение и заработную плату.</span><span class="sxs-lookup"><span data-stu-id="fcb49-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="fcb49-110">Структура позволяет сделать это в одной переменной.</span><span class="sxs-lookup"><span data-stu-id="fcb49-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="fcb49-111">Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="fcb49-111">To declare a structure</span></span>  
  
1. <span data-ttu-id="fcb49-112">Создайте начальную и конечную инструкции для структуры.</span><span class="sxs-lookup"><span data-stu-id="fcb49-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="fcb49-113">Можно указать уровень доступа структуры с помощью ключевого слова [Public](../../../language-reference/modifiers/public.md), [protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)или [Private](../../../language-reference/modifiers/private.md) , либо можно разрешить по умолчанию использовать `Public` .</span><span class="sxs-lookup"><span data-stu-id="fcb49-113">You can specify the access level of a structure using the [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), or [Private](../../../language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="fcb49-114">Добавьте элементы в текст структуры.</span><span class="sxs-lookup"><span data-stu-id="fcb49-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="fcb49-115">Структура должна содержать по крайней мере один элемент.</span><span class="sxs-lookup"><span data-stu-id="fcb49-115">A structure must have at least one element.</span></span> <span data-ttu-id="fcb49-116">Необходимо объявить каждый элемент и указать для него уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="fcb49-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="fcb49-117">Если вы используете [инструкцию Dim](../../../language-reference/statements/dim-statement.md) без ключевых слов, для специальных возможностей по умолчанию используется значение `Public` .</span><span class="sxs-lookup"><span data-stu-id="fcb49-117">If you use the [Dim Statement](../../../language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     <span data-ttu-id="fcb49-118">`salary`Поле в предыдущем примере имеет значение `Private` , которое означает, что оно недоступно за пределами структуры, даже из содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="fcb49-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="fcb49-119">Однако `giveRaise` процедура является `Public` , поэтому ее можно вызывать извне структуры.</span><span class="sxs-lookup"><span data-stu-id="fcb49-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="fcb49-120">Аналогичным образом можно вызвать `salaryReviewTime` событие за пределами структуры.</span><span class="sxs-lookup"><span data-stu-id="fcb49-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="fcb49-121">Помимо переменных, процедур и `Sub` событий, в структуре можно также определять константы, `Function` процедуры и свойства.</span><span class="sxs-lookup"><span data-stu-id="fcb49-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="fcb49-122">Можно назначить не более одного свойства в качестве *свойства по умолчанию*при условии, что оно принимает по крайней мере один аргумент.</span><span class="sxs-lookup"><span data-stu-id="fcb49-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="fcb49-123">Можно выполнить обработку события с помощью [общей](../../../language-reference/modifiers/shared.md) `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="fcb49-123">You can handle an event with a [Shared](../../../language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="fcb49-124">Дополнительные сведения см. в разделе [инструкции. объявление и вызов свойства по умолчанию в Visual Basic](../procedures/how-to-declare-and-call-a-default-property.md).</span><span class="sxs-lookup"><span data-stu-id="fcb49-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb49-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fcb49-125">See also</span></span>

- [<span data-ttu-id="fcb49-126">Типы данных</span><span class="sxs-lookup"><span data-stu-id="fcb49-126">Data Types</span></span>](index.md)
- [<span data-ttu-id="fcb49-127">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="fcb49-127">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="fcb49-128">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="fcb49-128">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="fcb49-129">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="fcb49-129">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="fcb49-130">Структуры</span><span class="sxs-lookup"><span data-stu-id="fcb49-130">Structures</span></span>](structures.md)
- [<span data-ttu-id="fcb49-131">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="fcb49-131">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="fcb49-132">Переменные структуры</span><span class="sxs-lookup"><span data-stu-id="fcb49-132">Structure Variables</span></span>](structure-variables.md)
- [<span data-ttu-id="fcb49-133">Структуры и другие элементы программирования</span><span class="sxs-lookup"><span data-stu-id="fcb49-133">Structures and Other Programming Elements</span></span>](structures-and-other-programming-elements.md)
- [<span data-ttu-id="fcb49-134">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="fcb49-134">Structures and Classes</span></span>](structures-and-classes.md)
- [<span data-ttu-id="fcb49-135">Определяемый пользователем тип данных</span><span class="sxs-lookup"><span data-stu-id="fcb49-135">User-Defined Data Type</span></span>](../../../language-reference/data-types/user-defined-data-type.md)
