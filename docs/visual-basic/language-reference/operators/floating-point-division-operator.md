---
title: Оператор /
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: 765a80d45908e0ecf17e4c21b748dbf6b2a4c0f5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867034"
---
# <a name="-operator-visual-basic"></a>Оператор / (Visual Basic)

Делит одно число на другое и возвращает результат в виде числа с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a>Компоненты  

 `expression1`  
 Обязательный. Произвольное числовое выражение.  
  
 `expression2`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="supported-types"></a>Поддерживаемые типы  

 Все числовые типы, включая неподписанные и типы с плавающей запятой, и `Decimal` .  
  
## <a name="result"></a>Результат  

 Результатом является полное частное от деления на `expression1` `expression2` , включая остаток.  
  
 [Оператор \ (Visual Basic)](integer-division-operator.md) возвращает целочисленное частное, которое удаляет остаток.  
  
## <a name="remarks"></a>Remarks  

 Тип данных результата зависит от типов операндов. В следующей таблице показано, как определяется тип данных результата.  
  
|Типы данных операндов|Тип данных результата|  
|------------------------|----------------------|  
|Оба выражения являются целочисленными типами данных ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ulong](../data-types/ulong-data-type.md)).|`Double`|  
|Одно выражение имеет [один](../data-types/single-data-type.md) тип данных, а другой — не [Double](../data-types/double-data-type.md) .|`Single`|  
|Одно выражение имеет тип данных [Decimal](../data-types/decimal-data-type.md) , а второй не является [одиночным](../data-types/single-data-type.md) или [double](../data-types/double-data-type.md) .|`Decimal`|  
|Любое выражение является типом данных [Double](../data-types/double-data-type.md)|`Double`|  
  
 Перед выполнением деления все целочисленные числовые выражения расширяются до `Double` . Если результат присваивается целочисленному типу данных, Visual Basic пытается преобразовать результат из `Double` в этот тип. Это может вызвать исключение, если результат не умещается в этом типе. В частности, см. раздел "попыток деления на ноль" на этой странице справки.  
  
 Если `expression1` или `expression2` имеет значение [Nothing](../nothing.md), оно считается нулевым.  
  
## <a name="attempted-division-by-zero"></a>Попыток деления на ноль  

 Если `expression2` значение равно нулю, `/` оператор ведет себя по-разному для разных типов данных операндов. В следующей таблице показаны возможные варианты поведения.  
  
|Типы данных операндов|Поведение `expression2` , если равно нулю|  
|------------------------|---------------------------------------|  
|С плавающей запятой ( `Single` или `Double` )|Возвращает бесконечное значение ( <xref:System.Double.PositiveInfinity> или <xref:System.Double.NegativeInfinity> ) или <xref:System.Double.NaN> (не число), если `expression1` равно нулю|  
|`Decimal`|Создает <xref:System.DivideByZeroException>|  
|Интеграл (со знаком или без знака)|Попытка преобразования обратно в целочисленный тип вызывается <xref:System.OverflowException> из-за того, что целочисленные типы не могут принимать <xref:System.Double.PositiveInfinity> , <xref:System.Double.NegativeInfinity> или <xref:System.Double.NaN>|  
  
> [!NOTE]
> `/`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  

 В этом примере `/` оператор используется для выполнения деления с плавающей запятой. Результатом является частное двух операндов.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 Выражения в предыдущем примере возвращают значения 2,5 и 3,333333. Обратите внимание, что результат всегда имеет тип с плавающей запятой ( `Double` ), хотя оба операнда являются целочисленными константами.  
  
## <a name="see-also"></a>См. также

- [Оператор/= (Visual Basic)](floating-point-division-assignment-operator.md)
- [Оператор \ (Visual Basic)](integer-division-operator.md)
- [Типы данных результатов оператора](data-types-of-operator-results.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
