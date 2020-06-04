---
title: Тип данных Integer
ms.date: 01/31/2018
f1_keywords:
- vb.Integer
- Integer
helpviewer_keywords:
- numbers [Visual Basic], whole
- enumerated values [Visual Basic]
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- literal type characters [Visual Basic], I
- integers [Visual Basic], types
- data types [Visual Basic], integral
- '% identifier type character'
- data types [Visual Basic], assigning
- identifier type characters [Visual Basic], %
- I literal type character [Visual Basic]
- Integer data type
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
ms.openlocfilehash: aa7b64162308d6af2763b29034c5a7276c973876
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415613"
---
# <a name="integer-data-type-visual-basic"></a>Тип данных Integer (Visual Basic)

Содержит 32-разрядные (4-байтовые) целые числа со знаком в диапазоне от -2 147 483 648 до 2 147 483 647.  
  
## <a name="remarks"></a>Комментарии

 Тип данных `Integer` обеспечивает оптимальную производительность на 32-разрядных процессорах. Другие целочисленные типы загружаются в память и сохраняются в памяти с более низкой скоростью.  
  
 Значение по умолчанию для типа `Integer` — 0.  

## <a name="literal-assignments"></a>Присваивания литералов

Вы можете объявить и инициализировать `Integer` переменную, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `Integer` (то есть, если он меньше <xref:System.Int32.MinValue?displayProperty=nameWithType> или больше <xref:System.Int32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 90 946 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `Integer`.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> Используйте префикс `&h` или `&H` , чтобы обозначить шестнадцатеричный литерал, префикс `&b` или `&B` обозначить двоичный литерал, а также префикс `&o` или `&O` обозначить Восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания () в `_` качестве разделителя цифр, чтобы улучшить удобочитаемость, как показано в следующем примере.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания () в `_` качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы также могут включать `I` [символ типа](../../programming-guide/language-features/data-types/type-characters.md) для обозначения `Integer` типа данных, как показано в следующем примере.

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a>Советы по программированию

- **Вопросы взаимодействия.** При взаимоработе с компонентами, которые не записываются для .NET Framework, таких как автоматизация или COM-объекты, помните, что `Integer` в других средах ширина данных (16 бит) отличается. При передаче 16-разрядного аргумента такому компоненту в новом коде Visual Basic следует объявить его как `Short`, а не как `Integer`.  
  
- **Расширяющие.** Тип данных `Integer` можно расширить до `Long`, `Decimal`, `Single` или `Double`. Это означает, что тип `Integer` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Символы типа.** При добавлении к литералу символа типа литерала `I` производится принудительное приведение литерала к типу данных `Integer`. При добавлении символа идентификатора типа `%` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Integer`.  
  
- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Int32?displayProperty=nameWithType>.  
  
## <a name="range"></a>Диапазон

При попытке присвоить целочисленной переменной значение, лежащее за пределами диапазона данного типа, возникает ошибка. При попытке задать дробное значение оно округляется вверх или вниз до ближайшего целого значения. Если число находится точно посередине между двумя целыми числами, значение округляется до ближайшего четного целого. Такое поведение минимизирует ошибки округления, происходящие от постоянного округления среднего значения в одном направлении. В следующем коде приведены примеры округления.  

```vb  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```

## <a name="see-also"></a>См. также раздел

- <xref:System.Int32?displayProperty=nameWithType>
- [Типы данных](index.md)
- [Тип данных Long](long-data-type.md)
- [Тип данных Short](short-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
