---
description: 'Подробнее о: короткий тип данных (Visual Basic)'
title: Тип данных Short
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 8c6bee45355548b3a32d74d059159918b4009fbb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792145"
---
# <a name="short-data-type-visual-basic"></a>Короткий тип данных (Visual Basic)

Содержит 16-битные (2-байтные) целые числа со знаком в диапазоне от-32 768 до 32 767.  
  
## <a name="remarks"></a>Remarks  

 Используйте `Short` тип данных для хранения целочисленных значений, не требующих полной ширины данных `Integer` . В некоторых случаях среда CLR может `Short` объединять переменные и экономить потребление памяти.  
  
 Значение по умолчанию для типа `Short` — 0.  
  
## <a name="literal-assignments"></a>Присваивания литералов

Можно объявить и инициализировать `Short` переменную, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `Short` (то есть, если он меньше <xref:System.Int16.MinValue?displayProperty=nameWithType> или больше <xref:System.Int16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 1 034, представленные в виде десятичных, шестнадцатеричных и двоичных литералов, неявно преобразуются из [типа Integer](integer-data-type.md) в `Short` значения.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Используйте префикс `&h` или `&H` , чтобы обозначить шестнадцатеричный литерал, префикс `&b` или `&B` обозначить двоичный литерал, а также префикс `&o` или `&O` обозначить Восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания () в `_` качестве разделителя цифр, чтобы улучшить удобочитаемость, как показано в следующем примере.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания () в `_` качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример:

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы также могут включать `S` [символ типа](../../programming-guide/language-features/data-types/type-characters.md) для обозначения `Short` типа данных, как показано в следующем примере.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>Советы по программированию

- **Расширяющие.** `Short`Тип данных расширяется до `Integer` ,, `Long` , `Decimal` `Single` или `Double` . Это означает, что тип `Short` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=nameWithType>.  
  
- **Символы типа.** При добавлении к литералу символа типа литерала `S` производится принудительное приведение литерала к типу данных `Short`. `Short` не имеет символа типа идентификатора.  
  
- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Int16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Int16?displayProperty=nameWithType>
- [Типы данных](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Тип данных Integer](integer-data-type.md)
- [Тип данных Long](long-data-type.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
