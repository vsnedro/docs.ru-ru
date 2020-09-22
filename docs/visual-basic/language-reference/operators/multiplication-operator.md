---
title: '* Оператор'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 7038fef4258d190b726a851b26f2a2840ff3c0ea
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873362"
---
# <a name="-operator-visual-basic"></a>Оператор * (Visual Basic)

Перемножает два числа.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`number1`|Обязательный. Произвольное числовое выражение.|  
|`number2`|Обязательный. Произвольное числовое выражение.|  
  
## <a name="result"></a>Результат  

 Результатом является произведение `number1` и `number2` .  
  
## <a name="supported-types"></a>Поддерживаемые типы  

 Все числовые типы, включая неподписанные и типы с плавающей запятой, и `Decimal` .  
  
## <a name="remarks"></a>Remarks  

 Тип данных результата зависит от типов операндов. В следующей таблице показано, как определяется тип данных результата.  
  
|Типы данных операндов|Тип данных результата|  
|---|---|  
|Оба выражения являются целочисленными типами данных ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ulong](../data-types/ulong-data-type.md)).|Числовой тип данных, подходящий для типов данных `number1` и `number2` . См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](data-types-of-operator-results.md).|  
|Оба выражения являются [десятичными](../data-types/decimal-data-type.md)|`Decimal`|  
|Оба выражения являются [одиночными](../data-types/single-data-type.md)|`Single`|  
|Одно из выражений является типом данных с плавающей запятой ( `Single` или [Double](../data-types/double-data-type.md)), но не оба `Single` (Обратите внимание `Decimal` , что это не тип данных с плавающей запятой).|`Double`|  
  
 Если выражение принимает значение [Nothing](../nothing.md), оно считается нулевым.  
  
## <a name="overloading"></a>Перегрузка  

 `*`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  

 В этом примере `*` оператор используется для умножения двух чисел. Результатом является произведение двух операндов.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>См. также

- [Оператор * =](multiplication-assignment-operator.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
