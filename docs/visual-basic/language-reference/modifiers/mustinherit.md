---
title: MustInherit
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 84df7a5cfdad3b5bc6764675725a5d0cb402b0b7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396211"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="3caee-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3caee-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="3caee-103">Указывает, что класс может использоваться только в качестве базового класса и не может создавать объект непосредственно из него.</span><span class="sxs-lookup"><span data-stu-id="3caee-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3caee-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3caee-104">Remarks</span></span>  
 <span data-ttu-id="3caee-105">Целью *базового класса* (также известного как *абстрактный класс*) является определение функций, общих для всех классов, производных от него.</span><span class="sxs-lookup"><span data-stu-id="3caee-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="3caee-106">Это позволяет сохранить производные классы от необходимости переопределять общие элементы.</span><span class="sxs-lookup"><span data-stu-id="3caee-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="3caee-107">В некоторых случаях эта общая функциональность не является достаточно полной для создания пригодного для использования объекта, и каждый производный класс определяет недостающие функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="3caee-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="3caee-108">В этом случае необходимо, чтобы код, создающий объекты, был создан только из производных классов.</span><span class="sxs-lookup"><span data-stu-id="3caee-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="3caee-109">`MustInherit`Для этого используйте в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="3caee-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="3caee-110">Другим применением `MustInherit` класса является ограничение переменной набором связанных классов.</span><span class="sxs-lookup"><span data-stu-id="3caee-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="3caee-111">Можно определить базовый класс и получить от него все связанные с ним классы.</span><span class="sxs-lookup"><span data-stu-id="3caee-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="3caee-112">Базовый класс не обязан предоставлять функциональные возможности, общие для всех производных классов, но он может служить фильтром для присвоения значений переменным.</span><span class="sxs-lookup"><span data-stu-id="3caee-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="3caee-113">Если в используемом коде объявляется переменная в качестве базового класса, Visual Basic позволяет назначить этой переменной только один из производных классов.</span><span class="sxs-lookup"><span data-stu-id="3caee-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="3caee-114">.NET Framework определяет несколько `MustInherit` классов, между ними, <xref:System.Array> <xref:System.Enum> и <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="3caee-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="3caee-115"><xref:System.ValueType>— Это пример базового класса, который ограничивают переменную.</span><span class="sxs-lookup"><span data-stu-id="3caee-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="3caee-116">Все типы значений являются производными от <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="3caee-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="3caee-117">Если переменная объявляется как <xref:System.ValueType> , то этой переменной можно назначить только типы значений.</span><span class="sxs-lookup"><span data-stu-id="3caee-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3caee-118">Правила</span><span class="sxs-lookup"><span data-stu-id="3caee-118">Rules</span></span>  
  
- <span data-ttu-id="3caee-119">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="3caee-119">**Declaration Context.**</span></span> <span data-ttu-id="3caee-120">Можно использовать `MustInherit` только в `Class` операторе.</span><span class="sxs-lookup"><span data-stu-id="3caee-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="3caee-121">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="3caee-121">**Combined Modifiers.**</span></span> <span data-ttu-id="3caee-122">Нельзя указывать `MustInherit` вместе с `NotInheritable` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="3caee-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3caee-123">Пример</span><span class="sxs-lookup"><span data-stu-id="3caee-123">Example</span></span>  
 <span data-ttu-id="3caee-124">В следующем примере показано принудительное наследование и принудительное переопределение.</span><span class="sxs-lookup"><span data-stu-id="3caee-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="3caee-125">Базовый класс `shape` определяет переменную `acrossLine` .</span><span class="sxs-lookup"><span data-stu-id="3caee-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="3caee-126">Классы `circle` и `square` являются производными от `shape` .</span><span class="sxs-lookup"><span data-stu-id="3caee-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="3caee-127">Они наследуют определение `acrossLine` , но они должны определять функцию, `area` так как это вычисление различается для каждого вида фигуры.</span><span class="sxs-lookup"><span data-stu-id="3caee-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="3caee-128">Можно объявлять `shape1` и `shape2` иметь тип `shape` .</span><span class="sxs-lookup"><span data-stu-id="3caee-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="3caee-129">Однако нельзя создать объект из, `shape` поскольку он не имеет функций функции `area` и помечен как `MustInherit` .</span><span class="sxs-lookup"><span data-stu-id="3caee-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="3caee-130">Поскольку они объявляются как `shape` , переменные `shape1` и `shape2` ограничены объектами из производных классов `circle` и `square` .</span><span class="sxs-lookup"><span data-stu-id="3caee-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="3caee-131">Visual Basic не позволяет назначать другим объектам эти переменные, что обеспечивает высокий уровень безопасности типов.</span><span class="sxs-lookup"><span data-stu-id="3caee-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="3caee-132">Использование</span><span class="sxs-lookup"><span data-stu-id="3caee-132">Usage</span></span>  
 <span data-ttu-id="3caee-133">`MustInherit`Модификатор можно использовать в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="3caee-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="3caee-134">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="3caee-134">Class Statement</span></span>](../statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3caee-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3caee-135">See also</span></span>

- [<span data-ttu-id="3caee-136">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="3caee-136">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="3caee-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="3caee-137">NotInheritable</span></span>](notinheritable.md)
- [<span data-ttu-id="3caee-138">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3caee-138">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="3caee-139">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="3caee-139">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
