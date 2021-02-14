---
description: 'Подробнее: арифметические операторы в Visual Basic'
title: Арифметические операторы
ms.date: 07/20/2015
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
ms.openlocfilehash: 3a7005b0a44f9b0358e393d8580a2a19a9a19881
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100465331"
---
# <a name="arithmetic-operators-in-visual-basic"></a>Арифметические операторы в Visual Basic

Арифметические операторы используются для выполнения многих знакомых арифметических операций, использующих вычисление числовых значений, представленных литералами, переменными, другими выражениями, вызовами функций и свойств и констант. Кроме того, классификация с помощью арифметических операторов — это операторы сдвига в битах, которые действуют на уровне отдельных битов операндов и сдвигаются их битовые шаблоны влево или вправо.  
  
## <a name="arithmetic-operations"></a>Арифметические операции  

 Можно добавить два значения в выражение вместе с [оператором +](../../../language-reference/operators/addition-operator.md)или вычесть одно из другого с помощью [оператора-operator (Visual Basic)](../../../language-reference/operators/subtraction-operator.md), как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 Отрицание также использует [оператор-operator (Visual Basic)](../../../language-reference/operators/subtraction-operator.md), но только с одним операндом, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 При умножении и разделении используются [оператор *](../../../language-reference/operators/multiplication-operator.md) и [оператор (Visual Basic)](../../../language-reference/operators/floating-point-division-operator.md)соответственно, как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 В возведение в степень используется [оператор ^](../../../language-reference/operators/exponentiation-operator.md), как показано в следующем примере.  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 Целочисленное деление выполняется с помощью [оператора \ (Visual Basic)](../../../language-reference/operators/integer-division-operator.md). Целочисленное деление Возвращает частное, то есть целое число, представляющее количество, которое делитель может разделить на делимое, без учета остатка. Делитель и делимое должны быть целочисленными типами ( `SByte` , `Byte` ,,,, `Short` `UShort` `Integer` `UInteger` , `Long` и `ULong` ) для этого оператора. Сначала необходимо преобразовать все остальные типы в целочисленный тип. В следующем примере показано целочисленное деление.  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 Арифметическая операция деления выполняется с помощью [оператора MOD](../../../language-reference/operators/mod-operator.md). Этот оператор возвращает остаток от деления делителя на делимое на целое число раз. Если и делитель, и делим являются целочисленными типами, возвращаемое значение является целочисленным. Если делитель и делимые являются типами с плавающей запятой, возвращаемое значение также будет плавающей запятой. Следующий пример демонстрирует эту ситуацию.  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a>Попыток деления на ноль  

 Деление на ноль приводит к различным результатам в зависимости от используемых типов данных. В целочисленных подразделениях ( `SByte` , `Byte` , `Short` ,,,, `UShort` `Integer` `UInteger` `Long` , `ULong` ) платформа .NET Framework создает <xref:System.DivideByZeroException> исключение. В операциях деления для `Decimal` `Single` типа данных или платформа .NET Framework также вызывает <xref:System.DivideByZeroException> исключение.  
  
 В подразделениях с плавающей запятой, включающих `Double` тип данных, исключение не создается, а результатом является член класса <xref:System.Double.NaN> , представляющий, <xref:System.Double.PositiveInfinity> или <xref:System.Double.NegativeInfinity> , в зависимости от делимого. В следующей таблице перечислены различные результаты попытки деления `Double` значения на ноль.  
  
|Тип данных делимого|Тип данных делителя|Делимое значение|Результат|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN> (не является математически определенным числом)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 При перехвате <xref:System.DivideByZeroException> исключения можно использовать его члены, чтобы помочь в его обработке. Например, <xref:System.Exception.Message%2A> свойство содержит текст сообщения для исключения. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="bit-shift-operations"></a>Bit-Shift операции  

 Операция сдвига в битах выполняет арифметический сдвиг для битового шаблона. Шаблон содержится в операнде слева, а операнд справа указывает количество позиций для сдвига шаблона. Можно сдвинуть шаблон вправо с помощью [ оператора>> ](../../../language-reference/operators/right-shift-operator.md) или слева с помощью [ оператора<< ](../../../language-reference/operators/left-shift-operator.md).  
  
 Тип данных операнда шаблона должен быть `SByte` , `Byte` ,,, `Short` `UShort` `Integer` , `UInteger` , `Long` или `ULong` . Тип данных операнда суммы сдвига должен быть `Integer` или должен быть расширен до `Integer` .  
  
 Арифметические сдвиги не являются циклическими, то есть биты, сдвинутые за пределы результата, не переносятся на другой конец. Позиции битов, освобожденные сдвигом, устанавливаются следующим образом:  
  
- 0 для арифметического сдвига влево  
  
- 0 для арифметического сдвига вправо положительного числа  
  
- 0 для арифметического сдвига вправо неподписанного типа данных ( `Byte` , `UShort` , `UInteger` , `ULong` )  
  
- 1 для арифметического сдвига вправо отрицательного числа ( `SByte` , `Short` , `Integer` или `Long` )  
  
 В следующем примере `Integer` значение сдвигается влево и вправо.  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 Арифметические сдвиги никогда не создают исключений переполнения.  
  
## <a name="bitwise-operations"></a>Битовые операции  

 В дополнение к логическим операторам,,, `Not` `Or` `And` и `Xor` также выполняют побитовую арифметическую операцию при использовании числовых значений. Дополнительные сведения см. в разделе "битовые операции" в [логических и побитовых операторах в Visual Basic](logical-and-bitwise-operators.md).  
  
## <a name="type-safety"></a>Безопасность типов  

 Обычно операнды должны иметь один и тот же тип. Например, если вы делаете сложение с `Integer` переменной, то следует добавить ее в другую `Integer` переменную, а результат также следует присвоить переменной типа `Integer` .  
  
 Одним из способов обеспечения хорошей строгой типизации кода является использование [оператора Option строго](../../../language-reference/statements/option-strict-statement.md). Если задано `Option Strict On` , Visual Basic автоматически выполняет строго *типизированные* преобразования. Например, если попытаться добавить `Integer` переменную в `Double` переменную и присвоить ей значение `Double` , операция выполняется обычным образом, так как `Integer` значение может быть преобразовано в `Double` без потери данных. Типы-ненадежные преобразования, с другой стороны, вызывают ошибку компилятора с `Option Strict On` . Например, при попытке добавить `Integer` переменную в `Double` переменную и присвоить ей значение `Integer` , результатом ошибки компилятора является то, что `Double` переменная не может быть неявно преобразована в тип `Integer` .  
  
 Однако если задать `Option Strict Off` , то Visual Basic допускает неявные сужающие преобразования, хотя они могут привести к непредвиденной утрате данных или точности. По этой причине рекомендуется использовать `Option Strict On` при написании рабочего кода. Для получения дополнительной информации см. [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).  
  
## <a name="see-also"></a>См. также раздел

- [Арифметические операторы](../../../language-reference/operators/arithmetic-operators.md)
- [Операторы сдвига битов](../../../language-reference/operators/bit-shift-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Операторы объединения в Visual Basic](concatenation-operators.md)
- [Логические и побитовые операторы в Visual Basic](logical-and-bitwise-operators.md)
- [Эффективное сочетание операторов](efficient-combination-of-operators.md)
