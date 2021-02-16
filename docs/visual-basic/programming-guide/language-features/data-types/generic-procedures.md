---
description: Дополнительные сведения об общих процедурах см. в Visual Basic
title: Универсальные процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: c8f26d66f7b657e00382ea94ed0d6093211a3e96
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434710"
---
# <a name="generic-procedures-in-visual-basic"></a>Generic Procedures in Visual Basic

*Универсальная процедура*, также называемая *универсальным методом*, представляет собой процедуру, определенную по крайней мере с одним параметром типа. Это позволяет вызывающему коду адаптировать типы данных к их требованиям при каждом вызове процедуры.  
  
 Процедура не является универсальной просто путем определения внутри универсального класса или универсальной структуры. Как универсальное, процедура должна принимать по крайней мере один параметр типа в дополнение к обычным параметрам, которые он может принимать. Универсальный класс или структура может содержать неуниверсальные процедуры, а неуниверсальный класс, структура или модуль могут содержать универсальные процедуры.  
  
 Универсальная процедура может использовать свои параметры-типы в его стандартном списке параметров, в его возвращаемом типе, если он есть, и в коде процедуры.  
  
## <a name="type-inference"></a>Вывод типа  

 Можно вызвать универсальную процедуру без указания каких-либо аргументов типа. При таком вызове компилятор пытается определить подходящие типы данных для передачи аргументам типа процедуры. Это называется *выводом типа*. В следующем коде показан вызов, в котором компилятор определяет, что он должен передать тип `String` в параметр типа `t` .  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 Если компилятор не может вывести аргументы типа из контекста вызова, он сообщает об ошибке. Одной из возможных причин такой ошибки является несоответствие ранга массива. Например, предположим, что вы определили нормальный параметр в качестве массива параметра типа. При вызове универсальной процедуры, предоставляющей массив другого ранга (число измерений), несоответствие приводит к сбою определения типа. В следующем коде показан вызов, в котором двумерный массив передается в процедуру, которая принимает одномерный массив.  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 Вывод типа можно вызвать только путем пропуска всех аргументов типа. При указании одного аргумента типа необходимо указать все эти аргументы.  
  
 Вывод типа поддерживается только для универсальных процедур. Невозможно вызвать определение типа в универсальных классах, структурах, интерфейсах или делегатах.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  

 В следующем примере определяется универсальная `Function` процедура поиска определенного элемента в массиве. Он определяет один параметр типа и использует его для создания двух параметров в списке параметров.  
  
### <a name="code"></a>Код  

 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a>Комментарии  

 В предыдущем примере требуется возможность сравнения с `searchValue` каждым элементом `searchArray` . Чтобы гарантировать эту возможность, он ограничивает параметр типа `T` для реализации <xref:System.IComparable%601> интерфейса. В коде используется <xref:System.IComparable%601.CompareTo%2A> метод вместо `=` оператора, поскольку нет никакой гарантии, что аргумент типа предоставляется для `T` поддержки `=` оператора.  
  
 Процедуру можно проверить `findElement` с помощью следующего кода.  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 Предыдущие вызовы для `MsgBox` отображают "0", "1" и "-1" соответственно.  
  
## <a name="see-also"></a>См. также раздел

- [Generic Types in Visual Basic](generic-types.md)
- [Практическое руководство. Определение класса, реализующего одинаковую функциональность для разных типов данных](how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Практическое руководство. Использование универсального класса](how-to-use-a-generic-class.md)
- [Процедуры](../procedures/index.md)
- [Параметры и аргументы процедуры](../procedures/procedure-parameters-and-arguments.md)
- [Type List](../../../language-reference/statements/type-list.md)
- [Список параметров](../../../language-reference/statements/parameter-list.md)
