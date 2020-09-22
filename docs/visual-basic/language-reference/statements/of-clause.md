---
title: Предложение Of
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: 0595356fb75fc0ac73a49622d71fe1d28fa7b648
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865900"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="1f87b-102">Предложение Of (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f87b-102">Of Clause (Visual Basic)</span></span>

<span data-ttu-id="1f87b-103">Вводит `Of` предложение, которое определяет *параметр типа* в *универсальном* классе, структуре, интерфейсе, делегате или процедуре.</span><span class="sxs-lookup"><span data-stu-id="1f87b-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="1f87b-104">Сведения об универсальных типах см. [в разделе Универсальные типы в Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="1f87b-104">For information on generic types, see [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="1f87b-105">Использование ключевого слова of</span><span class="sxs-lookup"><span data-stu-id="1f87b-105">Using the Of Keyword</span></span>  

 <span data-ttu-id="1f87b-106">В следующем примере кода `Of` ключевое слово используется для определения структуры класса, принимающего два параметра типа.</span><span class="sxs-lookup"><span data-stu-id="1f87b-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="1f87b-107">Он *ограничивает* `keyType` параметр <xref:System.IComparable> интерфейсом, что означает, что в используемом коде должен быть указан аргумент типа, реализующий <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="1f87b-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="1f87b-108">Это необходимо для того, чтобы `add` процедура могла вызвать <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="1f87b-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1f87b-109">Дополнительные сведения об ограничениях см. в разделе [Type List](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="1f87b-109">For more information on constraints, see [Type List](type-list.md).</span></span>  
  
```vb  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="1f87b-110">Если вы закончите предыдущее определение класса, можно создать `dictionary` из него разнообразные классы.</span><span class="sxs-lookup"><span data-stu-id="1f87b-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="1f87b-111">Предоставленные типы `entryType` и определяют, `keyType` какой тип записи принадлежит классу и какой тип ключа он связывает с каждой записью.</span><span class="sxs-lookup"><span data-stu-id="1f87b-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="1f87b-112">Из-за ограничения необходимо указать `keyType` тип, реализующий <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="1f87b-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="1f87b-113">В следующем примере кода создается объект, который содержит `String` записи и связывает `Integer` ключ с каждым из них.</span><span class="sxs-lookup"><span data-stu-id="1f87b-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="1f87b-114">`Integer` реализует <xref:System.IComparable> и поэтому удовлетворяет ограничению для `keyType` .</span><span class="sxs-lookup"><span data-stu-id="1f87b-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="1f87b-115">Ключевое слово `Of` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="1f87b-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="1f87b-116">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="1f87b-116">Class Statement</span></span>](class-statement.md)  
  
 [<span data-ttu-id="1f87b-117">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="1f87b-117">Delegate Statement</span></span>](delegate-statement.md)  
  
 [<span data-ttu-id="1f87b-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="1f87b-118">Function Statement</span></span>](function-statement.md)  
  
 [<span data-ttu-id="1f87b-119">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="1f87b-119">Interface Statement</span></span>](interface-statement.md)  
  
 [<span data-ttu-id="1f87b-120">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="1f87b-120">Structure Statement</span></span>](structure-statement.md)  
  
 [<span data-ttu-id="1f87b-121">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="1f87b-121">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1f87b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1f87b-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="1f87b-123">Type List</span><span class="sxs-lookup"><span data-stu-id="1f87b-123">Type List</span></span>](type-list.md)
- [<span data-ttu-id="1f87b-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f87b-124">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="1f87b-125">Где</span><span class="sxs-lookup"><span data-stu-id="1f87b-125">In</span></span>](../modifiers/in-generic-modifier.md)
- [<span data-ttu-id="1f87b-126">Заполняет</span><span class="sxs-lookup"><span data-stu-id="1f87b-126">Out</span></span>](../modifiers/out-generic-modifier.md)
