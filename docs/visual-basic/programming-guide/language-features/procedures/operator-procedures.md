---
description: 'Дополнительные сведения: процедуры оператора (Visual Basic)'
title: Процедуры операторов
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 836eeb2e705a96c49b5fa53e277ccf025d1915b2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100479963"
---
# <a name="operator-procedures-visual-basic"></a>Процедуры операторов (Visual Basic)

Процедура оператора — это ряд инструкций Visual Basic, которые определяют поведение стандартного оператора (например `*` ,, `<>` или `And` ) для определенного класса или структуры. Это также называется *перегрузкой операторов*.

## <a name="when-to-define-operator-procedures"></a>Когда следует определять процедуры оператора

Определив класс или структуру, можно объявить переменные, имеющие тип этого класса или структуры. Иногда такая переменная должна участвовать в операции как часть выражения. Для этого он должен быть операндом оператора.

Visual Basic определяет операторы только для основных типов данных. Поведение оператора можно определить, если один или оба операнда имеют тип класса или структуры.

Дополнительные сведения см. в разделе Оператор [operator](../../../language-reference/statements/operator-statement.md).

## <a name="types-of-operator-procedure"></a>Типы процедур операторов

Процедура оператора может иметь один из следующих типов:

- Определение унарного оператора, где аргумент имеет тип класса или структуры.

- Определение бинарного оператора, в котором по крайней мере один из аргументов имеет тип класса или структуры.

- Определение оператора преобразования, в котором аргумент имеет тип класса или структуры.

- Определение оператора преобразования, возвращающего тип класса или структуры.

 Операторы преобразования всегда являются унарными, и всегда используются в `CType` качестве оператора, который вы определяете.

## <a name="declaration-syntax"></a>Синтаксис объявления

Синтаксис для объявления процедуры оператора выглядит следующим образом:

```vb
Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype

' Statements of the operator procedure.

End Operator
```

`Widening` `Narrowing` Ключевое слово или используется только для оператора преобразования типа. Символ оператора всегда является [функцией CType](../../../language-reference/functions/ctype-function.md) для оператора преобразования типа.

Вы объявляете два операнда для определения бинарного оператора и объявляете один операнд для определения унарного оператора, включая оператор преобразования типа. Все операнды должны быть объявлены `ByVal` .

Каждый операнд объявляется точно так же, как вы объявляете параметры для [процедур подраздела](./sub-procedures.md).

### <a name="data-type"></a>Тип данных

Поскольку вы определяете оператор для определенного класса или структуры, по крайней мере один из операндов должен иметь тип данных этого класса или структуры. Для оператора преобразования типа операнд или возвращаемый тип должен иметь тип данных класса или структуры.

Дополнительные сведения см. в разделе Оператор [operator](../../../language-reference/statements/operator-statement.md).

## <a name="calling-syntax"></a>Синтаксис вызова

Процедуру оператора можно вызвать неявно, используя символ оператора в выражении. Операнды указываются так же, как и для предопределенных операторов.

Для неявного вызова процедуры оператора используется следующий синтаксис:

`Dim testStruct As`  *structurename*

`Dim testNewStruct As`  *structurename* `= testStruct` *операторсимбол*      `10`

### <a name="illustration-of-declaration-and-call"></a>Иллюстрация объявления и вызова

В следующей структуре хранится 128-разрядное целое число со знаком в качестве составляющих элементов высокого и нижнего порядка. Он определяет `+` оператор для добавления двух `veryLong` значений и формирования результирующего `veryLong` значения.

[!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]

В следующем примере показан типичный вызов оператора, `+` определенного для `veryLong` .

[!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]

## <a name="see-also"></a>См. также раздел

- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры функций](./function-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Практическое руководство. Определение оператора](./how-to-define-an-operator.md)
- [Практическое руководство. Определение оператора преобразования](./how-to-define-a-conversion-operator.md)
- [Практическое руководство. Вызов процедуры оператора](./how-to-call-an-operator-procedure.md)
- [Практическое руководство. Использование класса, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md)
