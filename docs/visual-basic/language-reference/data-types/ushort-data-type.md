---
description: 'Дополнительные сведения: тип данных UShort (Visual Basic)'
title: Тип данных UShort
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: 43c18bad3e24e14c28d2ca3d5d88170d584e55a8
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106648"
---
# <a name="ushort-data-type-visual-basic"></a>Тип данных UShort (Visual Basic)

Содержит 16-разрядные (2-байтные) целые числа без знака в диапазоне от 0 до 65 535.  
  
## <a name="remarks"></a>Комментарии

 Используйте `UShort` тип данных для хранения двоичных данных, размер которых слишком велик `Byte` .  
  
 Значение по умолчанию для типа `UShort` — 0.  

## <a name="literal-assignments"></a>Присваивания литералов

Можно объявить и инициализировать `UShort` переменную, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `UShort` (то есть, если он меньше <xref:System.UInt16.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 65 034, представленные в виде десятичных, шестнадцатеричных и двоичных литералов, присваиваются `UShort` значениям.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Используйте префикс `&h` или `&H` , чтобы обозначить шестнадцатеричный литерал, префикс `&b` или `&B` обозначить двоичный литерал, а также префикс `&o` или `&O` обозначить Восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания () в `_` качестве разделителя цифр, чтобы улучшить удобочитаемость, как показано в следующем примере.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания () в `_` качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы также могут включать `US` `us` [символ типа](../../programming-guide/language-features/data-types/type-characters.md) или для обозначения `UShort` типа данных, как показано в следующем примере.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Советы по программированию
  
- **Отрицательные числа.** Так как `UShort` является неподписанным типом, он не может представлять отрицательное число. При использовании оператора унарного минуса ( `-` ) в выражении, результатом которого является тип `UShort` , Visual Basic преобразует выражение в `Integer` First.  
  
- **Соответствие CLS.** `UShort`Тип данных не является частью [спецификации](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) CLS, поэтому CLS-совместимый код не может использовать компонент, который его использует.
  
- **Расширяющие.** `UShort`Тип данных расширяется до `Integer` ,,,,, `UInteger` `Long` `ULong` `Decimal` `Single` и `Double` . Это означает, что можно преобразовать `UShort` в любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.  
  
- **Символы типа.** При добавлении символов типа литерала `US` к литералу он применяет его к `UShort` типу данных. `UShort` не имеет символа типа идентификатора.  
  
- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.UInt16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.UInt16>
- [Типы данных](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
