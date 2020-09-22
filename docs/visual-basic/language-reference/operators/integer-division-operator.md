---
title: Оператор \
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: cf2dc66532925d56cea6fd141f44a245bc2dd8dd
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873394"
---
# <a name="-operator-visual-basic"></a>Оператор \ (Visual Basic)

Делит одно число на другое и возвращает целочисленный результат.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a>Компоненты  

 `expression1`  
 Обязательный. Произвольное числовое выражение.  
  
 `expression2`  
 Обязательный. Произвольное числовое выражение.  
  
## <a name="supported-types"></a>Поддерживаемые типы  

 Все числовые типы, включая неподписанные и типы с плавающей запятой, и `Decimal` .  
  
## <a name="result"></a>Результат  

 Результатом является целочисленное частное `expression1` деление на `expression2` , которое отклоняет остаток и оставляет только целую часть. Это называется *усечением*.  
  
 Тип данных result является числовым типом, подходящим для типов данных `expression1` и `expression2` . См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](data-types-of-operator-results.md).  
  
 [Оператор/(Visual Basic)](floating-point-division-operator.md) возвращает полное частное, сохраняющее остаток в дробной части.  
  
## <a name="remarks"></a>Remarks  

 Перед выполнением деления Visual Basic пытается преобразовать любое числовое выражение с плавающей запятой в `Long` . Если `Option Strict` имеет значение `On` , возникает ошибка компилятора. Если параметр `Option Strict` имеет `Off` значение, то <xref:System.OverflowException> возможно, если значения выходят за пределы диапазона [данных типа Long](../data-types/long-data-type.md). Преобразование в `Long` также регулируется *округлением банка*. Дополнительные сведения см. в разделе "Дробные части" [функций преобразования типов](../functions/type-conversion-functions.md).  
  
 Если `expression1` или `expression2` имеет значение [Nothing](../nothing.md), оно считается нулевым.  
  
## <a name="attempted-division-by-zero"></a>Попыток деления на ноль  

 Если `expression2` значение равно нулю, `\` оператор выдает <xref:System.DivideByZeroException> исключение. Это справедливо для всех числовых типов данных операндов.  
  
> [!NOTE]
> `\`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `\` для выполнения целочисленного деления. Результатом является целое число, представляющее целочисленное частное двух операндов с отброшенным остатком.  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 Выражения в предыдущем примере возвращают значения 2, 3, 33 и-22 соответственно.  
  
## <a name="see-also"></a>См. также

- [\\Оператор =](integer-division-assignment-operator.md)
- [Оператор/(Visual Basic)](floating-point-division-operator.md)
- [Оператор Option Strict](../statements/option-strict-statement.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
