---
title: Объявление объектной переменной
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: 74b1401df3dbb2d744de74734d10cbcd92e9689e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077050"
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="ad505-102">Объявление переменных объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad505-102">Object Variable Declaration (Visual Basic)</span></span>

<span data-ttu-id="ad505-103">Для объявления объектной переменной используется стандартный оператор объявления.</span><span class="sxs-lookup"><span data-stu-id="ad505-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="ad505-104">Для типа данных указывается либо `Object` (то есть [тип данных Object](../../../language-reference/data-types/object-data-type.md)), либо более конкретный класс, из которого будет создан объект.</span><span class="sxs-lookup"><span data-stu-id="ad505-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="ad505-105">Объявление переменной как аналогично объявлению `Object` ее как <xref:System.Object?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ad505-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="ad505-106">При объявлении переменной с конкретным классом объектов он может получить доступ ко всем методам и свойствам, предоставляемым этим классом, и классами, от которых он наследуется.</span><span class="sxs-lookup"><span data-stu-id="ad505-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="ad505-107">Если объявить переменную с <xref:System.Object> , она может обращаться только к членам <xref:System.Object> класса, если не `Option Strict Off` разрешить позднее связывание.</span><span class="sxs-lookup"><span data-stu-id="ad505-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="ad505-108">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="ad505-108">Declaration Syntax</span></span>  

 <span data-ttu-id="ad505-109">Для объявления объектной переменной используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ad505-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="ad505-110">В объявлении также можно указать [открытые](../../../language-reference/modifiers/public.md), [защищенные](../../../language-reference/modifiers/protected.md), [дружественные](../../../language-reference/modifiers/friend.md), `Protected Friend` [частные](../../../language-reference/modifiers/private.md), [Общие](../../../language-reference/modifiers/shared.md)или [статические](../../../language-reference/modifiers/static.md) .</span><span class="sxs-lookup"><span data-stu-id="ad505-110">You can also specify [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../language-reference/modifiers/private.md), [Shared](../../../language-reference/modifiers/shared.md), or [Static](../../../language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="ad505-111">Допустимы следующие примеры объявлений:</span><span class="sxs-lookup"><span data-stu-id="ad505-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="ad505-112">Позднее связывание и раннее связывание</span><span class="sxs-lookup"><span data-stu-id="ad505-112">Late Binding and Early Binding</span></span>  

 <span data-ttu-id="ad505-113">Иногда конкретный класс неизвестен, пока не будет запущен код.</span><span class="sxs-lookup"><span data-stu-id="ad505-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="ad505-114">В этом случае необходимо объявить объектную переменную с `Object` типом данных.</span><span class="sxs-lookup"><span data-stu-id="ad505-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="ad505-115">При этом создается общая ссылка на объект любого типа, а конкретный класс назначается во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad505-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="ad505-116">Это называется *поздним связыванием*.</span><span class="sxs-lookup"><span data-stu-id="ad505-116">This is called *late binding*.</span></span> <span data-ttu-id="ad505-117">Позднее связывание требует дополнительного времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad505-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="ad505-118">Он также ограничивает ваш код методами и свойствами класса, назначенного ему последним.</span><span class="sxs-lookup"><span data-stu-id="ad505-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="ad505-119">Это может вызвать ошибки времени выполнения, если код пытается получить доступ к членам другого класса.</span><span class="sxs-lookup"><span data-stu-id="ad505-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="ad505-120">Когда вы узнаете конкретный класс во время компиляции, следует объявить переменную объекта для этого класса.</span><span class="sxs-lookup"><span data-stu-id="ad505-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="ad505-121">Этот принцип называется *раннее связывание*.</span><span class="sxs-lookup"><span data-stu-id="ad505-121">This is called *early binding*.</span></span> <span data-ttu-id="ad505-122">Раннее связывание повышает производительность и гарантирует доступ кода ко всем методам и свойствам конкретного класса.</span><span class="sxs-lookup"><span data-stu-id="ad505-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="ad505-123">В приведенных выше примерах объявлений, если переменная `objA` использует только объекты класса <xref:System.Windows.Forms.Label?displayProperty=nameWithType> , `As System.Windows.Forms.Label` в его объявлении следует указать.</span><span class="sxs-lookup"><span data-stu-id="ad505-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="ad505-124">Преимущества раннего связывания</span><span class="sxs-lookup"><span data-stu-id="ad505-124">Advantages of Early Binding</span></span>  

 <span data-ttu-id="ad505-125">Объявление объектной переменной в качестве конкретного класса дает несколько преимуществ:</span><span class="sxs-lookup"><span data-stu-id="ad505-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
- <span data-ttu-id="ad505-126">Автоматическая проверка типов</span><span class="sxs-lookup"><span data-stu-id="ad505-126">Automatic type checking</span></span>  
  
- <span data-ttu-id="ad505-127">Гарантированный доступ ко всем членам указанного класса</span><span class="sxs-lookup"><span data-stu-id="ad505-127">Guaranteed access to all members of the specific class</span></span>  
  
- <span data-ttu-id="ad505-128">Поддержка Microsoft IntelliSense в редакторе кода</span><span class="sxs-lookup"><span data-stu-id="ad505-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
- <span data-ttu-id="ad505-129">Улучшенная удобочитаемость кода</span><span class="sxs-lookup"><span data-stu-id="ad505-129">Improved readability of your code</span></span>  
  
- <span data-ttu-id="ad505-130">Меньше ошибок в коде</span><span class="sxs-lookup"><span data-stu-id="ad505-130">Fewer errors in your code</span></span>  
  
- <span data-ttu-id="ad505-131">Ошибки, перехваченные во время компиляции, а не во время выполнения</span><span class="sxs-lookup"><span data-stu-id="ad505-131">Errors caught at compile time rather than run time</span></span>  
  
- <span data-ttu-id="ad505-132">Ускорение выполнения кода</span><span class="sxs-lookup"><span data-stu-id="ad505-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="ad505-133">Доступ к членам переменных объектов</span><span class="sxs-lookup"><span data-stu-id="ad505-133">Access to Object Variable Members</span></span>  

 <span data-ttu-id="ad505-134">Если параметр `Option Strict` включен `On` , переменная объекта может обращаться только к методам и свойствам класса, с которым он объявлен.</span><span class="sxs-lookup"><span data-stu-id="ad505-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="ad505-135">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ad505-135">The following example illustrates this.</span></span>  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 <span data-ttu-id="ad505-136">В этом примере `p` может использовать только члены класса <xref:System.Object> без свойства `Left` .</span><span class="sxs-lookup"><span data-stu-id="ad505-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="ad505-137">С другой стороны, `q` был объявлен с типом <xref:System.Windows.Forms.Label>, поэтому он может использовать все методы и свойства класса <xref:System.Windows.Forms.Label> в пространстве имен <xref:System.Windows.Forms> .</span><span class="sxs-lookup"><span data-stu-id="ad505-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="ad505-138">Гибкость объектных переменных</span><span class="sxs-lookup"><span data-stu-id="ad505-138">Flexibility of Object Variables</span></span>  

 <span data-ttu-id="ad505-139">При работе с объектами в иерархии наследования можно выбрать, какой класс использовать для объявления переменных объекта.</span><span class="sxs-lookup"><span data-stu-id="ad505-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="ad505-140">При выборе этого варианта необходимо сбалансировать гибкость назначения объектов для доступа к членам класса.</span><span class="sxs-lookup"><span data-stu-id="ad505-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="ad505-141">Например, рассмотрим иерархию наследования, которая ведет к <xref:System.Windows.Forms.Form?displayProperty=nameWithType> классу:</span><span class="sxs-lookup"><span data-stu-id="ad505-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="ad505-142">Предположим, что приложение определяет класс формы с именем `specialForm` , который наследует от класса <xref:System.Windows.Forms.Form> .</span><span class="sxs-lookup"><span data-stu-id="ad505-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="ad505-143">Можно объявить переменную объекта, которая ссылается специально на `specialForm` , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ad505-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="ad505-144">Объявление в предыдущем примере ограничивает переменную `nextForm` на объекты класса `specialForm` , но также делает все методы и свойства `specialForm` доступными для `nextForm` , а также все члены всех классов, от которых `specialForm` наследуется.</span><span class="sxs-lookup"><span data-stu-id="ad505-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="ad505-145">Можно сделать переменную объекта более общей, объявив ее <xref:System.Windows.Forms.Form> как тип, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ad505-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="ad505-146">Объявление в предыдущем примере позволяет назначить любую форму в приложении `anyForm` .</span><span class="sxs-lookup"><span data-stu-id="ad505-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="ad505-147">Однако несмотря на то, что `anyForm` имеет доступ ко всем членам класса <xref:System.Windows.Forms.Form> , он не может использовать дополнительные методы или свойства, определенные для определенных форм, таких как `specialForm` .</span><span class="sxs-lookup"><span data-stu-id="ad505-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="ad505-148">Все члены базового класса доступны для производных классов, но дополнительные члены производного класса недоступны для базового класса.</span><span class="sxs-lookup"><span data-stu-id="ad505-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad505-149">См. также</span><span class="sxs-lookup"><span data-stu-id="ad505-149">See also</span></span>

- [<span data-ttu-id="ad505-150">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="ad505-150">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="ad505-151">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="ad505-151">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="ad505-152">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="ad505-152">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="ad505-153">Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта</span><span class="sxs-lookup"><span data-stu-id="ad505-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="ad505-154">Практическое руководство. Доступ к членам объекта</span><span class="sxs-lookup"><span data-stu-id="ad505-154">How to: Access Members of an Object</span></span>](how-to-access-members-of-an-object.md)
- [<span data-ttu-id="ad505-155">Оператор New</span><span class="sxs-lookup"><span data-stu-id="ad505-155">New Operator</span></span>](../../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="ad505-156">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="ad505-156">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="ad505-157">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="ad505-157">Local Type Inference</span></span>](local-type-inference.md)
