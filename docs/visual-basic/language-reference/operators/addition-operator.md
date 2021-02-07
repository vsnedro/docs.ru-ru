---
description: 'Дополнительные сведения о операторе: + (Visual Basic)'
title: + Оператор
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: 9a6517847945cb2edcbd97adac6a013498dde174
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700693"
---
# <a name="-operator-visual-basic"></a>Оператор + (Visual Basic)

Складывает два числа или возвращает положительное значение числового выражения. Также можно использовать для сцепления двух строковых выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb
expression1 + expression2
```
  
or

```vb  
+expression1  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`expression1`|Обязательный. Любое числовое или строковое выражение.|  
|`expression2`|Требуется, если `+` оператор не вычисляет отрицательное значение. Любое числовое или строковое выражение.|  
  
## <a name="result"></a>Результат  

 Если `expression1` и `expression2` являются числовыми, результатом является их арифметическая сумма.  
  
 Если параметр отсутствует `expression2` , `+` оператор является *унарным* оператором идентификации для неизменного значения выражения. В этом смысле операция состоит из удержания знака `expression1` , поэтому результат будет отрицательным, если `expression1` имеет отрицательное значение.  
  
 Если `expression1` и `expression2` являются строками, результатом является объединение их значений.  
  
 Если `expression1` и `expression2` имеют смешанные типы, то выполняемое действие зависит от их типов, их содержимого и значения, установленного в [операторе Option](../statements/option-strict-statement.md). Дополнительные сведения см. в таблицах в разделе "Примечания".  
  
## <a name="supported-types"></a>Поддерживаемые типы  

 Все числовые типы, включая неподписанные и типы с плавающей запятой `Decimal` , и `String` .  
  
## <a name="remarks"></a>Remarks  

 Как правило, `+` выполняет арифметическое сложение, когда это возможно, и объединяет только в том случае, если оба выражения являются строками.  
  
 Если ни одно из выражений не является `Object` , Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|Оба выражения являются числовыми типами данных ( `SByte` ,, `Byte` ,, `Short` `UShort` `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` или `Double` ).|Добавить. Тип данных result является числовым типом, подходящим для типов данных `expression1` и `expression2` . См. таблицу "целочисленные арифметические операции" в [типах данных результатов операторов](data-types-of-operator-results.md).|  
|Оба выражения имеют тип `String`|Объединения.|  
|Одно выражение является числовым типом данных, а второй — строкой|Если `Option Strict` имеет значение `On` , то генерируется ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off` , то неявно преобразует в `String` `Double` и добавьте.<br /><br /> Если `String` не удается преобразовать в `Double` , вызовите <xref:System.InvalidCastException> исключение.|  
|Одно выражение имеет числовой тип данных, а другой — [Nothing](../nothing.md) .|Добавьте со `Nothing` значением 0.|  
|Одно выражение — строка, а другая — `Nothing`|Объединение со `Nothing` значением "".|  
  
 Если одно выражение является `Object` выражением, Visual Basic выполняет следующие действия.  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|`Object` выражение содержит числовое значение, а другое — числовой тип данных|Если `Option Strict` имеет значение `On` , то генерируется ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off` , добавьте.|  
|`Object` выражение содержит числовое значение, а другое имеет тип `String`|Если `Option Strict` имеет значение `On` , то генерируется ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off` , то неявно преобразует в `String` `Double` и добавьте.<br /><br /> Если `String` не удается преобразовать в `Double` , вызовите <xref:System.InvalidCastException> исключение.|  
|`Object` выражение содержит строку, а другая — числовой тип данных|Если `Option Strict` имеет значение `On` , то генерируется ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off` , то неявно преобразует строку `Object` в `Double` и добавьте.<br /><br /> Если строка `Object` не может быть преобразована в `Double` , возникает <xref:System.InvalidCastException> исключение.|  
|`Object` выражение содержит строку, а другая — тип `String`|Если `Option Strict` имеет значение `On` , то генерируется ошибка компилятора.<br /><br /> Если `Option Strict` имеет значение `Off` , то неявное преобразование `Object` в `String` и сцепление.|  
  
 Если оба выражения являются `Object` выражениями, Visual Basic выполняет следующие действия ( `Option Strict Off` только).  
  
|Типы данных выражений|Действие по компилятору|  
|---|---|  
|Оба `Object` выражения содержат числовые значения|Добавить.|  
|Оба `Object` выражения имеют тип `String`|Объединения.|  
|Одно `Object` выражение содержит числовое значение, а другое содержит строку.|Неявным образом Преобразуйте строку `Object` в `Double` и добавьте.<br /><br /> Если строка `Object` не может быть преобразована в числовое значение, то возникает <xref:System.InvalidCastException> исключение.|  
  
 Если любое из `Object` выражений имеет значение [Nothing](../nothing.md) или <xref:System.DBNull> , `+` оператор обрабатывает его как `String` со значением "".  
  
> [!NOTE]
> При использовании `+` оператора может быть невозможно определить, будет ли выполняться сложение или объединение строк. Используйте `&` оператор для объединения, чтобы исключить неоднозначность и предоставить код для самостоятельного документирования.  
  
## <a name="overloading"></a>Перегрузка  

 `+`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `+` для добавления чисел. Если операнды являются числовыми, Visual Basic вычислит арифметический результат. Арифметический результат представляет сумму двух операндов.  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 Можно также использовать `+` оператор для сцепления строк. Если операнды являются строками, Visual Basic сцепляет их. Результат объединения представляет собой одну строку, состоящую из содержимого двух операндов, один за другим.  
  
 Если операнды имеют смешанные типы, результат зависит от значения параметра [Option Case](../statements/option-strict-statement.md). В следующем примере показан результат, если `Option Strict` имеет значение `On` .  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 В следующем примере показан результат, если `Option Strict` имеет значение `Off` .  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 Чтобы избежать неоднозначности, следует использовать `&` оператор вместо `+` для объединения.  
  
## <a name="see-also"></a>См. также

- [ Оператор&](concatenation-operator.md)
- [Операторы объединения](concatenation-operators.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Арифметические операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Оператор Option Strict](../statements/option-strict-statement.md)
