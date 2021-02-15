---
description: 'Дополнительные сведения: операторы объединения в Visual Basic'
title: Операторы объединения
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: 7d007a830e4547f87e937cc7313c248485b4b574
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476401"
---
# <a name="concatenation-operators-in-visual-basic"></a>Операторы объединения в Visual Basic

Операторы объединения объединяют несколько строк в одну. Существует два оператора объединения: `+` и `&`. Оба они выполняют базовую операцию объединения, как показано в следующем примере.

```vb
Dim x As String = "Mic" & "ro" & "soft"
Dim y As String = "Mic" + "ro" + "soft"
' The preceding statements set both x and y to "Microsoft".
```

Эти операторы также могут объединять переменные `String`, как показано в следующем примере.

[!code-vb[VbVbalrOperators#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#76)]

## <a name="differences-between-the-two-concatenation-operators"></a>Различия между двумя операторами объединения

[Оператор +](../../../language-reference/operators/addition-operator.md) имеет основную цель сложения двух чисел. Однако он также может объединять числовые операнды со строковыми. Оператор `+` имеет сложный набор правил, определяющий, следует ли выполнять добавление, объединение, сигнализировать об ошибке компилятора или выдавать исключение времени выполнения <xref:System.InvalidCastException>.

[Оператор&](../../../language-reference/operators/concatenation-operator.md) определен только для `String` операндов и всегда расширяет его операнды до `String` , независимо от значения параметра `Option Strict` . Оператор `&` рекомендуется использовать для объединения строк, так как он определен исключительно для строк и снижает шансы создания непреднамеренного преобразования.

## <a name="performance-string-and-stringbuilder"></a>Производительность: String и StringBuilder

Если вы выполняете множество операций со строкой, таких как объединения, удаления и замены, использование класса <xref:System.Text.StringBuilder> из пространства имен <xref:System.Text> может оказать положительное влияние на производительность. Для создания и инициализации объекта <xref:System.Text.StringBuilder> требуется дополнительная инструкция, кроме того, еще одна инструкция необходима для преобразования итогового значения в `String`, однако это время можно скомпенсировать высокой скоростью выполнения <xref:System.Text.StringBuilder>.

## <a name="see-also"></a>См. также раздел

- [Оператор Option Strict](../../../language-reference/statements/option-strict-statement.md)
- [Типы методов для работы со строками в Visual Basic](../strings/types-of-string-manipulation-methods.md)
- [Арифметические операторы в Visual Basic](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Логические и побитовые операторы в Visual Basic](logical-and-bitwise-operators.md)
