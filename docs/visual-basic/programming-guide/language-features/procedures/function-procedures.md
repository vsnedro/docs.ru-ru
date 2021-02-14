---
description: 'Дополнительные сведения о процедурах: Function (Visual Basic)'
title: процедуры функций
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 4997059fc33fb5d438519356b2c9fdd9e6a27cce
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436153"
---
# <a name="function-procedures-visual-basic"></a>Процедуры Function (Visual Basic)

`Function`Процедура — это последовательность инструкций Visual Basic, заключенных в `Function` операторы и `End Function` . `Function`Процедура выполняет задачу, а затем возвращает управление вызывающему коду. Когда он возвращает управление, он также возвращает значение в вызывающий код.

При каждом вызове процедуры ее инструкции выполняются, начиная с первого исполняемого оператора после `Function` инструкции и заканчивая первой `End Function` `Exit Function` `Return` инструкцией, или.

Процедуру можно определить `Function` в модуле, классе или структуре. `Public`По умолчанию это означает, что вы можете вызывать его из любого места в приложении, которое имеет доступ к модулю, классу или структуре, в которой он определен.

`Function`Процедура может принимать аргументы, такие как константы, переменные или выражения, которые передаются в него вызывающим кодом.

## <a name="declaration-syntax"></a>Синтаксис объявления

Синтаксис для объявления `Function` процедуры выглядит следующим образом:

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

*Модификаторы* могут указывать уровень доступа и сведения о перегрузке, переопределении, совместном использовании и затенении. Дополнительные сведения см. в разделе [оператор Function](../../../language-reference/statements/function-statement.md).

Каждый параметр объявляется так же, как и для [процедур подраздела](./sub-procedures.md).

### <a name="data-type"></a>Тип данных

Каждая `Function` процедура имеет тип данных, точно так же, как и каждая переменная. Этот тип данных указывается `As` предложением в `Function` операторе и определяет тип данных значения, возвращаемого функцией в вызывающий код. Это показано в приведенных ниже примерах объявлений.

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

Дополнительные сведения см. в разделе "части" в [операторе Function](../../../language-reference/statements/function-statement.md).

### <a name="returning-values"></a>Возвращаемые значения

Значение, которое `Function` процедура отправляет обратно вызывающему коду, называется его возвращаемым значением. Процедура возвращает это значение одним из двух способов:

- Он использует `Return` инструкцию для указания возвращаемого значения и немедленно возвращает управление вызывающей программе. Это показано в следующем примере.

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- Он присваивает значение имени своей функции в одной или нескольких инструкциях процедуры. Управление не возвращается вызывающей программе до тех пор, `Exit Function` пока `End Function` не будет выполнен оператор или. Это показано в следующем примере.

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

Преимуществом присвоения возвращаемого значения имени функции является то, что Управление не возвращается из процедуры до тех пор, пока не встретится `Exit Function` `End Function` оператор или. Это позволяет назначить предварительное значение и позже при необходимости изменить его.

Дополнительные сведения о возвращаемых значениях см. в разделе [оператор Function](../../../language-reference/statements/function-statement.md). Дополнительные сведения о возврате массивов см. в разделе [массивы](../arrays/index.md).

## <a name="calling-syntax"></a>Синтаксис вызова

Процедура вызывается `Function` путем включения ее имени и аргументов в правой части оператора присваивания или в выражении. Необходимо указать значения для всех аргументов, которые не являются необязательными, и необходимо заключить список аргументов в круглые скобки. Если аргументы не указаны, можно дополнительно опустить круглые скобки.

Синтаксис для вызова процедуры выглядит следующим образом `Function` .

*lvalue* `=` *FunctionName* `[(` *ArgumentList*    `)]`

`If ((`*FunctionName* `[(` *ArgumentList* `)] / 3) <=` *выражение*  `) Then`

При вызове `Function` процедуры не нужно использовать ее возвращаемое значение. В противном случае выполняются все действия функции, но возвращаемое значение игнорируется. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> часто вызывается подобным образом.

### <a name="illustration-of-declaration-and-call"></a>Иллюстрация объявления и вызова

Следующая `Function` процедура вычисляет самую длинную сторону (гипотенузу) правого треугольника, учитывая значения двух других сторон.

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

В следующем примере показан типичный вызов метода `hypotenuse` .

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a>См. также раздел

- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Процедуры свойств](./property-procedures.md)
- [Процедуры операторов](./operator-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Function](../../../language-reference/statements/function-statement.md)
- [Практическое руководство. Создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)
- [Практическое руководство. Возврат значения из процедуры](./how-to-return-a-value-from-a-procedure.md)
- [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
