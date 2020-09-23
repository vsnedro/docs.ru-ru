---
title: Определение типа объекта
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: ae338bc9bad9646abc045a652d4ef33a8863354b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086066"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="f18be-102">Определение типа объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f18be-102">Determining Object Type (Visual Basic)</span></span>

<span data-ttu-id="f18be-103">Универсальные объектные переменные (то есть переменные, объявляемые как `Object` ) могут содержать объекты из любого класса.</span><span class="sxs-lookup"><span data-stu-id="f18be-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="f18be-104">При использовании переменных типа `Object` может потребоваться выполнить различные действия на основе класса объекта. Например, некоторые объекты могут не поддерживать конкретное свойство или метод.</span><span class="sxs-lookup"><span data-stu-id="f18be-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="f18be-105">Visual Basic предоставляет два способа определения типа объекта, хранящегося в объектной переменной: `TypeName` функции и `TypeOf...Is` оператора.</span><span class="sxs-lookup"><span data-stu-id="f18be-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="f18be-106">TypeName и TypeOf... Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="f18be-106">TypeName and TypeOf…Is</span></span>  

 <span data-ttu-id="f18be-107">`TypeName`Функция возвращает строку и является лучшим выбором, если необходимо сохранить или отобразить имя класса объекта, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="f18be-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="f18be-108">`TypeOf...Is`Оператор является лучшим выбором для тестирования типа объекта, так как он гораздо быстрее, чем эквивалентное сравнение строк с помощью `TypeName` .</span><span class="sxs-lookup"><span data-stu-id="f18be-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="f18be-109">В следующем фрагменте кода используется `TypeOf...Is` `If...Then...Else` оператор:</span><span class="sxs-lookup"><span data-stu-id="f18be-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="f18be-110">В этом случае следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="f18be-110">A word of caution is due here.</span></span> <span data-ttu-id="f18be-111">`TypeOf...Is`Оператор возвращает значение `True` , если объект относится к определенному типу или является производным от определенного типа.</span><span class="sxs-lookup"><span data-stu-id="f18be-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="f18be-112">Почти все, что выполняется с Visual Basic, включает объекты, которые включают в себя некоторые элементы, которые обычно не считаются объектами, например строками и целыми числами.</span><span class="sxs-lookup"><span data-stu-id="f18be-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="f18be-113">Эти объекты являются производными от методов и наследуют от них <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="f18be-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="f18be-114">Если передается `Integer` и вычисляется с помощью `Object` , `TypeOf...Is` оператор возвращает `True` .</span><span class="sxs-lookup"><span data-stu-id="f18be-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="f18be-115">В следующем примере сообщается, что параметр `InParam` является `Object` и, и `Integer` :</span><span class="sxs-lookup"><span data-stu-id="f18be-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="f18be-116">В следующем примере используются методы `TypeOf...Is` и `TypeName` для определения типа объекта, переданного в него в `Ctrl` аргументе.</span><span class="sxs-lookup"><span data-stu-id="f18be-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="f18be-117">`TestObject`Процедура вызывается `ShowType` с тремя различными видами элементов управления.</span><span class="sxs-lookup"><span data-stu-id="f18be-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="f18be-118">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="f18be-118">To run the example</span></span>  
  
1. <span data-ttu-id="f18be-119">Создайте новый проект приложения Windows и добавьте в <xref:System.Windows.Forms.Button> форму элемент управления, <xref:System.Windows.Forms.CheckBox> элемент управления и <xref:System.Windows.Forms.RadioButton> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="f18be-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2. <span data-ttu-id="f18be-120">В форме нажмите кнопку, чтобы вызвать `TestObject` процедуру.</span><span class="sxs-lookup"><span data-stu-id="f18be-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3. <span data-ttu-id="f18be-121">Добавьте в форму следующий код:</span><span class="sxs-lookup"><span data-stu-id="f18be-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="f18be-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f18be-122">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="f18be-123">Вызов свойства или метода с помощью строкового имени</span><span class="sxs-lookup"><span data-stu-id="f18be-123">Calling a Property or Method Using a String Name</span></span>](calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="f18be-124">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="f18be-124">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="f18be-125">Оператор If…Then…Else</span><span class="sxs-lookup"><span data-stu-id="f18be-125">If...Then...Else Statement</span></span>](../../../language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="f18be-126">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="f18be-126">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="f18be-127">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="f18be-127">Integer Data Type</span></span>](../../../language-reference/data-types/integer-data-type.md)
