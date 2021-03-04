---
description: 'Дополнительные сведения: тип данных SByte (Visual Basic)'
title: Тип данных SByte
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: a6a63ec742cf4a93080c9cc2f9906c5c6c21f0a8
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102102897"
---
# <a name="sbyte-data-type-visual-basic"></a>Тип данных SByte (Visual Basic)

Содержит 8-битные (1-байтные) целые числа со знаком в диапазоне от-128 до 127.

## <a name="remarks"></a>Комментарии

Используйте `SByte` тип данных для хранения целочисленных значений, не требующих полной ширины данных `Integer` или даже половины ширины данных `Short` . В некоторых случаях среда CLR может `SByte` одновременно упаковать переменные и сэкономить потребление памяти.

Значение по умолчанию для типа `SByte` — 0.

## <a name="literal-assignments"></a>Присваивания литералов

Вы можете объявить и инициализировать `SByte` переменную, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал.

В следующем примере целые числа, равные-102, представленные в виде десятичных, шестнадцатеричных и двоичных литералов, присваиваются `SByte` значениям. В этом примере требуется компилировать с `/removeintchecks` параметром компилятора.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Используйте префикс `&h` или `&H` , чтобы обозначить шестнадцатеричный литерал, префикс `&b` или `&B` обозначить двоичный литерал, а также префикс `&o` или `&O` обозначить Восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания () в `_` качестве разделителя цифр, чтобы улучшить удобочитаемость, как показано в следующем примере.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания () в `_` качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Если целочисленный литерал выходит за пределы диапазона `SByte` (то есть, если он меньше <xref:System.SByte.MinValue?displayProperty=nameWithType> или больше <xref:System.SByte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции. Если у целочисленного литерала нет суффикса, выводится [целое число](integer-data-type.md) . Если целочисленный литерал находится за пределами диапазона `Integer` типа, выводится значение [Long](long-data-type.md) . Это означает, что в предыдущих примерах числовые литералы и обрабатываются `0x9A` `0b10011010` как 32-разрядные целые числа со знаком со значением 156, что превышает <xref:System.SByte.MaxValue?displayProperty=nameWithType> . Чтобы успешно скомпилировать код, подобный этому, который присваивает недесятичное целое число `SByte` , можно выполнить одно из следующих действий.

- Отключает проверку целочисленных границ путем компиляции с `/removeintchecks` переключателем компилятора.

- Используйте [символ типа](../../programming-guide/language-features/data-types/type-characters.md) , чтобы явно определить литеральное значение, которое нужно присвоить `SByte` . В следующем примере для переназначается отрицательное литеральное `Short` значение `SByte` . Обратите внимание, что для отрицательных чисел необходимо задать старшие разрядные слова в числовом литерале с высоким порядком. В нашем примере это бит 15 литерального `Short` значения.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Советы по программированию

- **Соответствие CLS.** `SByte`Тип данных не является частью [спецификации](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) CLS, поэтому CLS-совместимый код не может использовать компонент, который его использует.

- **Расширяющие.** `SByte`Тип данных расширяется до `Short` , `Integer` ,,, `Long` `Decimal` `Single` и `Double` . Это означает, что можно преобразовать `SByte` в любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.

- **Символы типа.** `SByte` не имеет символа типа литерала или символа типа идентификатора.

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.SByte?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также раздел

- <xref:System.SByte?displayProperty=nameWithType>
- [Типы данных](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Тип данных Short](short-data-type.md)
- [Тип данных Integer](integer-data-type.md)
- [Тип данных Long](long-data-type.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
