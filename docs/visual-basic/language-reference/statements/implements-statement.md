---
title: Оператор Implements
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: b982057d2094f807b68d5190dfad388fb9a2c65a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873237"
---
# <a name="implements-statement"></a><span data-ttu-id="17e8e-102">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="17e8e-102">Implements Statement</span></span>

<span data-ttu-id="17e8e-103">Указывает один или несколько интерфейсов или элементов интерфейса, которые должны быть реализованы в определении класса или структуры, в котором они отображаются.</span><span class="sxs-lookup"><span data-stu-id="17e8e-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17e8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17e8e-104">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="17e8e-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="17e8e-105">Parts</span></span>  

 `interfacename`  
 <span data-ttu-id="17e8e-106">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="17e8e-106">Required.</span></span> <span data-ttu-id="17e8e-107">Интерфейс, свойства, процедуры и события которого должны быть реализованы соответствующими элементами в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="17e8e-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="17e8e-108">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="17e8e-108">Required.</span></span> <span data-ttu-id="17e8e-109">Член реализуемого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="17e8e-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17e8e-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="17e8e-110">Remarks</span></span>  

 <span data-ttu-id="17e8e-111">Интерфейс — это коллекция прототипов, представляющих члены (свойства, процедуры и события), которые инкапсулирует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="17e8e-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="17e8e-112">Интерфейсы содержат только объявления для членов; классы и структуры реализуют эти члены.</span><span class="sxs-lookup"><span data-stu-id="17e8e-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="17e8e-113">Дополнительные сведения см. в разделе [Интерфейсы](../../programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="17e8e-113">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="17e8e-114">`Implements`Оператор должен следовать непосредственно за `Class` `Structure` оператором или.</span><span class="sxs-lookup"><span data-stu-id="17e8e-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="17e8e-115">При реализации интерфейса необходимо реализовать все члены, объявленные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="17e8e-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="17e8e-116">Пропуск любого члена считается синтаксической ошибкой.</span><span class="sxs-lookup"><span data-stu-id="17e8e-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="17e8e-117">Для реализации отдельного элемента необходимо указать ключевое слово [Implements](implements-clause.md) (отдельно от `Implements` оператора) при объявлении члена в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="17e8e-117">To implement an individual member, you specify the [Implements](implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="17e8e-118">Дополнительные сведения см. в разделе [Интерфейсы](../../programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="17e8e-118">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="17e8e-119">Классы могут использовать [закрытые](../modifiers/private.md) реализации свойств и процедур, но эти члены доступны только путем приведения экземпляра реализующего класса к переменной, объявленной как тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="17e8e-119">Classes can use [Private](../modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17e8e-120">Пример</span><span class="sxs-lookup"><span data-stu-id="17e8e-120">Example</span></span>  

 <span data-ttu-id="17e8e-121">В следующем примере показано, как использовать `Implements` инструкцию для реализации членов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="17e8e-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="17e8e-122">Он определяет интерфейс с именем `ICustomerInfo` с событием, свойством и процедурой.</span><span class="sxs-lookup"><span data-stu-id="17e8e-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="17e8e-123">Класс `customerInfo` реализует все члены, определенные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="17e8e-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="17e8e-124">Обратите внимание, что класс `customerInfo` использует `Implements` оператор в отдельной строке исходного кода, чтобы указать, что класс реализует все члены `ICustomerInfo` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="17e8e-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="17e8e-125">Затем каждый член класса использует `Implements` ключевое слово как часть его объявления члена, чтобы указать, что он реализует этот член интерфейса.</span><span class="sxs-lookup"><span data-stu-id="17e8e-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17e8e-126">Пример</span><span class="sxs-lookup"><span data-stu-id="17e8e-126">Example</span></span>  

 <span data-ttu-id="17e8e-127">В следующих двух процедурах показано, как можно использовать интерфейс, реализованный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="17e8e-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="17e8e-128">Чтобы протестировать реализацию, добавьте эти процедуры в проект и вызовите `testImplements` процедуру.</span><span class="sxs-lookup"><span data-stu-id="17e8e-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="17e8e-129">См. также</span><span class="sxs-lookup"><span data-stu-id="17e8e-129">See also</span></span>

- [<span data-ttu-id="17e8e-130">Реализации</span><span class="sxs-lookup"><span data-stu-id="17e8e-130">Implements</span></span>](implements-clause.md)
- [<span data-ttu-id="17e8e-131">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="17e8e-131">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="17e8e-132">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="17e8e-132">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
