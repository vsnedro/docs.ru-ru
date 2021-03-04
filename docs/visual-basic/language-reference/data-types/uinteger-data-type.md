---
description: Дополнительные сведения о типе данных "UInteger"
title: Тип данных UInteger
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: c3c04f746f0e2cf15bc1881544b93a538dbdc04e
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104839"
---
# <a name="uinteger-data-type"></a>UInteger - тип данных

Содержит 32-разрядные (4-байтные) целые числа без знака, имеющие значение от 0 до 4 294 967 295.

## <a name="remarks"></a>Комментарии

`UInteger`Тип данных предоставляет наибольшее значение без знака в наиболее эффективной ширине данных.

Значение по умолчанию для типа `UInteger` — 0.

## <a name="literal-assignments"></a>Присваивания литералов

Можно объявить и инициализировать `UInteger` переменную, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `UInteger` (то есть, если он меньше <xref:System.UInt32.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 3 000 000 000 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `UInteger`.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> Используйте префикс `&h` или `&H` , чтобы обозначить шестнадцатеричный литерал, префикс `&b` или `&B` обозначить двоичный литерал, а также префикс `&o` или `&O` обозначить Восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания () в `_` качестве разделителя цифр, чтобы улучшить удобочитаемость, как показано в следующем примере.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания () в `_` качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Числовые литералы также могут включать `UI` `ui` [символ типа](../../programming-guide/language-features/data-types/type-characters.md) или для обозначения `UInteger` типа данных, как показано в следующем примере.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>Советы по программированию

`UInteger` `Integer` Типы данных и обеспечивают оптимальную производительность на 32-разрядном процессоре, поскольку меньшие целочисленные типы ( `UShort` ,, `Short` `Byte` и `SByte` ), даже если они используют меньшее количество битов, занимают больше времени на загрузку, хранение и выборку.

- **Отрицательные числа.** Так как `UInteger` является неподписанным типом, он не может представлять отрицательное число. При использовании оператора унарного минуса ( `-` ) в выражении, результатом которого является тип `UInteger` , Visual Basic преобразует выражение в `Long` First.

- **Соответствие CLS.** `UInteger`Тип данных не является частью [спецификации](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/) CLS, поэтому CLS-совместимый код не может использовать компонент, который его использует.

- **Вопросы взаимодействия.** Если вы взаимодействуете с компонентами, которые не написаны для платформа .NET Framework, например автоматизации или COM-объекты, помните, что такие типы, как, `uint` могут иметь разную ширину данных (16 бит) в других средах. При передаче 16-разрядного аргумента в такой компонент объявите его как `UShort` вместо `UInteger` в управляемом коде Visual Basic.

- **Расширяющие.** `UInteger`Тип данных расширяется до `Long` , `ULong` , `Decimal` , `Single` и `Double` . Это означает, что можно преобразовать `UInteger` в любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.

- **Символы типа.** При добавлении символов типа литерала `UI` к литералу он применяет его к `UInteger` типу данных. `UInteger` не имеет символа типа идентификатора.

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.UInt32?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также раздел

- <xref:System.UInt32>
- [Типы данных](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
