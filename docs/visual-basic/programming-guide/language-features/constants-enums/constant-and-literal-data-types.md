---
title: Типы данных констант и литералов
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: b94259326b42104db05d9fc5bb09f686075d0759
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414535"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>Типы данных констант и литералов (Visual Basic)
Литерал — это значение, которое выражено как само по себе, а не как значение переменной или результат выражения, например число 3 или строка "Hello". Константа — это понятное имя, которое принимает место литерала и сохраняется в программе в отличие от переменной, значение которой может измениться.  
  
 Если [параметр Infer](../../../language-reference/statements/option-infer-statement.md) имеет значение `Off` и [параметр Option строго](../../../language-reference/statements/option-strict-statement.md) имеет значение `On` , необходимо явно объявить все константы с типом данных. В следующем примере тип данных `MyByte` явно объявлен как тип данных `Byte` :  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 Если `Option Infer` имеет значение `On` или `Option Strict` является `Off` , можно объявить константу без указания типа данных с `As` предложением. Компилятор определяет тип константы на основе типа выражения. Числовой целочисленный литерал по умолчанию приводится к `Integer` типу данных. Тип данных по умолчанию для чисел с плавающей запятой — `Double` , и ключевые слова `True` и `False` задают `Boolean` константу.  
  
## <a name="literals-and-type-coercion"></a>Литералы и приведение типов  
 В некоторых случаях может потребоваться принудительно применить литерал к конкретному типу данных. Например, при присваивании особо большого целочисленного значения литерала переменной типа `Decimal` . Следующий пример приводит к ошибке:  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 Эта ошибка возникает из представления литерала. `Decimal`Тип данных может содержать это значение, но литерал неявно представляется как `Long` , что не может.  
  
 Можно привести литерал к определенному типу данных двумя способами: путем добавления к нему символа типа или путем помещения его в окружающие символы. Символ типа или заключенные в него символы должны находиться непосредственно перед и/или следовать за литералом без промежуточного пробела или символов какого-либо типа.  
  
 Чтобы предыдущий пример работал, можно добавить `D` символ типа к литералу, что приводит к представлению в виде `Decimal` :  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 В следующем примере показано правильное использование символов типа и окружающих символов:  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 В следующей таблице показаны окружающие символы и символы типа, доступные в Visual Basic.  
  
|Тип данных|Вложенный символ|Символ добавленного типа|  
|---|---|---|  
|`Boolean`|(нет)|(нет)|  
|`Byte`|(нет)|(нет)|  
|`Char`|"|C|  
|`Date`|#|(нет)|  
|`Decimal`|(нет)|D или @|  
|`Double`|(нет)|R или #|  
|`Integer`|(нет)|I или%|  
|`Long`|(нет)|L или &|  
|`Short`|(нет)|S|  
|`Single`|(нет)|F или!|  
|`String`|"|(нет)|  
  
## <a name="see-also"></a>См. также раздел

- [Константы, определенные пользователем](user-defined-constants.md)
- [Практическое руководство. Объявление константы](how-to-declare-a-constant.md)
- [Общие сведения о константах](constants-overview.md)
- [Оператор Option Strict](../../../language-reference/statements/option-strict-statement.md)
- [Оператор Option Explicit](../../../language-reference/statements/option-explicit-statement.md)
- [Общие сведения о перечислениях](enumerations-overview.md)
- [Практическое руководство. Объявление перечисления](how-to-declare-enumerations.md)
- [Перечисления и уточнение имен](enumerations-and-name-qualification.md)
- [Типы данных](../../../language-reference/data-types/index.md)
- [Константы и перечисления](../../../language-reference/constants-and-enumerations.md)
