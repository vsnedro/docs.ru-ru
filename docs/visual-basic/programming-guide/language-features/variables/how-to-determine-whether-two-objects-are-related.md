---
title: Практическое руководство. Определение наличия связи между двумя объектами
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 30e88a21e737aa57513745899577381ed34151a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410468"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="6418d-102">Практическое руководство. Определение наличия связи между двумя объектами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6418d-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="6418d-103">Можно сравнить два объекта, чтобы определить связь между классами, из которых они были созданы.</span><span class="sxs-lookup"><span data-stu-id="6418d-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="6418d-104"><xref:System.Type.IsInstanceOfType%2A>Метод <xref:System.Type?displayProperty=nameWithType> класса возвращает значение `True` , если указанный класс наследуется от текущего класса, или если текущий тип является интерфейсом, поддерживаемым указанным классом.</span><span class="sxs-lookup"><span data-stu-id="6418d-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="6418d-105">Определение того, наследуется ли один объект от класса или интерфейса другого объекта</span><span class="sxs-lookup"><span data-stu-id="6418d-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="6418d-106">В объекте, который вы считаете, может быть базовым типом, вызовите <xref:System.Object.GetType%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="6418d-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="6418d-107">В <xref:System.Type?displayProperty=nameWithType> объекте, возвращенном методом <xref:System.Object.GetType%2A> , вызовите <xref:System.Type.IsInstanceOfType%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="6418d-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="6418d-108">В списке аргументов для <xref:System.Type.IsInstanceOfType%2A> Укажите объект, который может иметь производный тип.</span><span class="sxs-lookup"><span data-stu-id="6418d-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="6418d-109"><xref:System.Type.IsInstanceOfType%2A>Возвращает значение `True` , если тип его аргумента наследуется от <xref:System.Type?displayProperty=nameWithType> типа объекта.</span><span class="sxs-lookup"><span data-stu-id="6418d-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="6418d-110">Пример</span><span class="sxs-lookup"><span data-stu-id="6418d-110">Example</span></span>
 <span data-ttu-id="6418d-111">В следующем примере определяется, представляет ли один объект класс, производный от класса другого объекта.</span><span class="sxs-lookup"><span data-stu-id="6418d-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

```vb
Public Class baseClass
End Class
Public Class derivedClass : Inherits baseClass
End Class
Public Class testTheseClasses
    Public Sub seeIfRelated()
        Dim baseObj As Object = New baseClass()
        Dim derivedObj As Object = New derivedClass()
        Dim related As Boolean
        related = baseObj.GetType().IsInstanceOfType(derivedObj)
        MsgBox(CStr(related))
    End Sub
End Class
```

<span data-ttu-id="6418d-112">Обратите внимание на непредвиденное размещение двух переменных объекта в вызове <xref:System.Type.IsInstanceOfType%2A> .</span><span class="sxs-lookup"><span data-stu-id="6418d-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="6418d-113">Предполагаемый базовый тип используется для создания <xref:System.Type?displayProperty=nameWithType> класса, а предполагаемый производный тип передается в качестве аргумента в <xref:System.Type.IsInstanceOfType%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="6418d-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="6418d-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6418d-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="6418d-115">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="6418d-115">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="6418d-116">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="6418d-116">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="6418d-117">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="6418d-117">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="6418d-118">Практическое руководство. Определение идентичности двух объектов</span><span class="sxs-lookup"><span data-stu-id="6418d-118">How to: Determine Whether Two Objects Are Identical</span></span>](how-to-determine-whether-two-objects-are-identical.md)
