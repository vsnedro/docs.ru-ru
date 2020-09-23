---
title: Практическое руководство. Определение наличия связи между двумя объектами
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b33815d58b0ef40f7f75a6a41bb4b1eeef591859
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072227"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Практическое руководство. Определение наличия связи между двумя объектами (Visual Basic)

Можно сравнить два объекта, чтобы определить связь между классами, из которых они были созданы. <xref:System.Type.IsInstanceOfType%2A>Метод <xref:System.Type?displayProperty=nameWithType> класса возвращает значение `True` , если указанный класс наследуется от текущего класса, или если текущий тип является интерфейсом, поддерживаемым указанным классом.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Определение того, наследуется ли один объект от класса или интерфейса другого объекта

1. В объекте, который вы считаете, может быть базовым типом, вызовите <xref:System.Object.GetType%2A> метод.

2. В <xref:System.Type?displayProperty=nameWithType> объекте, возвращенном методом <xref:System.Object.GetType%2A> , вызовите <xref:System.Type.IsInstanceOfType%2A> метод.

3. В списке аргументов для <xref:System.Type.IsInstanceOfType%2A> Укажите объект, который может иметь производный тип.

    <xref:System.Type.IsInstanceOfType%2A> Возвращает значение `True` , если тип его аргумента наследуется от <xref:System.Type?displayProperty=nameWithType> типа объекта.

## <a name="example"></a>Пример

 В следующем примере определяется, представляет ли один объект класс, производный от класса другого объекта.

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

Обратите внимание на непредвиденное размещение двух переменных объекта в вызове <xref:System.Type.IsInstanceOfType%2A> . Предполагаемый базовый тип используется для создания <xref:System.Type?displayProperty=nameWithType> класса, а предполагаемый производный тип передается в качестве аргумента в <xref:System.Type.IsInstanceOfType%2A> метод.

## <a name="see-also"></a>См. также

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Объектные переменные](object-variables.md)
- [Значения объектных переменных](object-variable-values.md)
- [Практическое руководство. Определение идентичности двух объектов](how-to-determine-whether-two-objects-are-identical.md)
