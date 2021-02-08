---
description: 'Дополнительные сведения о предложении: of (Visual Basic)'
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
ms.openlocfilehash: d6002041a2fe8db5b07e12e9e396a65fde30b716
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768848"
---
# <a name="of-clause-visual-basic"></a>Предложение Of (Visual Basic)

Вводит `Of` предложение, которое определяет *параметр типа* в *универсальном* классе, структуре, интерфейсе, делегате или процедуре. Сведения об универсальных типах см. [в разделе Универсальные типы в Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Использование ключевого слова of  

 В следующем примере кода `Of` ключевое слово используется для определения структуры класса, принимающего два параметра типа. Он *ограничивает* `keyType` параметр <xref:System.IComparable> интерфейсом, что означает, что в используемом коде должен быть указан аргумент типа, реализующий <xref:System.IComparable> . Это необходимо для того, чтобы `add` процедура могла вызвать <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> метод. Дополнительные сведения об ограничениях см. в разделе [Type List](type-list.md).  
  
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
  
 Если вы закончите предыдущее определение класса, можно создать `dictionary` из него разнообразные классы. Предоставленные типы `entryType` и определяют, `keyType` какой тип записи принадлежит классу и какой тип ключа он связывает с каждой записью. Из-за ограничения необходимо указать `keyType` тип, реализующий <xref:System.IComparable> .  
  
 В следующем примере кода создается объект, который содержит `String` записи и связывает `Integer` ключ с каждым из них. `Integer` реализует <xref:System.IComparable> и поэтому удовлетворяет ограничению для `keyType` .  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 Ключевое слово `Of` можно использовать в следующих контекстах:  
  
 [Оператор Class](class-statement.md)  
  
 [Оператор Delegate](delegate-statement.md)  
  
 [Оператор Function](function-statement.md)  
  
 [Оператор Interface](interface-statement.md)  
  
 [Оператор Structure](structure-statement.md)  
  
 [Оператор Sub](sub-statement.md)  
  
## <a name="see-also"></a>См. также

- <xref:System.IComparable>
- [Type List](type-list.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Где](../modifiers/in-generic-modifier.md)
- [Out](../modifiers/out-generic-modifier.md)
