---
title: При копировании значения ByRef параметра <parametername> обратно в соответствующий аргумент тип <typename1> сужается в тип <typename2>
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: bac5f9a88df719bc64a8b0541f65e5912275866e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409755"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a>При копировании значения ByRef параметра \<parametername> обратно в соответствующий аргумент тип \<typename1> сужается в тип \<typename2>
Процедура вызывается с аргументом, который расширяется до соответствующего типа параметра, а преобразование из параметра в аргумент является сужением.  
  
 При определении класса или структуры можно определить один или несколько операторов преобразования для преобразования типа класса или структуры в другие типы. Можно также определить операторы обратного преобразования для преобразования других типов обратно в тип класса или структуры. При использовании типа класса или структуры в вызове процедуры Visual Basic могут использовать эти операторы преобразования для преобразования типа аргумента в тип соответствующего параметра.  
  
 При передаче аргумента [ByRef](../modifiers/byref.md)Visual Basic иногда копирует значение аргумента в локальную переменную в процедуре вместо передачи ссылки. В этом случае, когда процедура возвращает, Visual Basic необходимо скопировать значение локальной переменной обратно в аргумент в вызывающем коде.  
  
 Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется. Но если типы различаются, Visual Basic должны быть преобразованы в обоих направлениях. Если один из типов является типом класса или структуры, Visual Basic должен преобразовать его в другой тип и из него. Если одно из этих преобразований является расширяющим, то обратным преобразованием может быть сужение.  
  
 **Идентификатор ошибки:** BC32053  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- По возможности используйте аргумент вызова того же типа, что и параметр процедуры, поэтому Visual Basic не требуется выполнять преобразование.  
  
- Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не требуется возвращать значение в аргумент вызова, то определите параметр как [ByVal](../modifiers/byval.md) , а не `ByRef`.  
  
- Если необходимо вернуть значение в аргумент вызова, определите оператор обратного преобразования в качестве [расширяющего](../modifiers/widening.md), если это возможно.  
  
## <a name="see-also"></a>См. также раздел

- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Параметры и аргументы процедуры](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Передача аргументов по значению и по ссылке](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Процедуры операторов](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Operator Statement](../statements/operator-statement.md)
- [Практическое руководство. Определение оператора](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Преобразование типов в Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
