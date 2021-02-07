---
description: Дополнительные сведения о типе данных Byte (Visual Basic)
title: Тип данных Byte
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 983af36d8340b5df7ac44782bf56349901460c20
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731231"
---
# <a name="byte-data-type-visual-basic"></a>Тип данных Byte (Visual Basic)

Содержит 8-битные (1-байтные) целые числа без знака в диапазоне от 0 до 255.

## <a name="remarks"></a>Remarks

Используйте `Byte` тип данных для хранения двоичных данных.  
  
Значение по умолчанию для типа `Byte` — 0.

## <a name="literal-assignments"></a>Присваивания литералов

Можно объявить и инициализировать `Byte` переменную, назначив ей десятичный литерал, шестнадцатеричный литерал, Восьмеричный литерал или (начиная с Visual Basic 2017) двоичный литерал. Если целочисленный литерал находится вне диапазона `Byte` (то есть если он меньше <xref:System.Byte.MinValue?displayProperty=nameWithType> или больше <xref:System.Byte.MaxValue?displayProperty=nameWithType> ), возникает ошибка компиляции.

В следующем примере целые числа, равные 201, представленные в виде десятичных, шестнадцатеричных и двоичных литералов, неявно преобразуются из [типа Integer](integer-data-type.md) в `byte` значения.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Используйте префикс `&h` или `&H` , чтобы обозначить шестнадцатеричный литерал, префикс `&b` или `&B` обозначить двоичный литерал, а также префикс `&o` или `&O` обозначить Восьмеричный литерал. У десятичных литералов префиксов нет.

Начиная с Visual Basic 2017, можно также использовать символ подчеркивания () в `_` качестве разделителя цифр, чтобы улучшить удобочитаемость, как показано в следующем примере.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Начиная с Visual Basic 15,5, можно также использовать символ подчеркивания () в `_` качестве начального разделителя между префиксом и шестнадцатеричными, двоичными или восьмеричными цифрами. Пример:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Советы по программированию

- **Отрицательные числа.** Так как `Byte` является неподписанным типом, он не может представлять отрицательное число. При использовании оператора унарного минуса ( `-` ) в выражении, результатом которого является тип `Byte` , Visual Basic преобразует выражение в `Short` First.
  
- **Преобразования формата.** Когда Visual Basic считывает или записывает файлы или вызывает библиотеки DLL, методы и свойства, он может автоматически выполнять преобразование между форматами данных. Двоичные данные, хранящиеся в `Byte` переменных и массивах, сохраняются во время таких преобразований формата. Не следует использовать `String` переменную для двоичных данных, так как ее содержимое может быть повреждено во время преобразования между форматами ANSI и Юникод.

- **Расширяющие.** `Byte`Тип данных расширяется до `Short` , `UShort` ,,, `Integer` `UInteger` `Long` , `ULong` , `Decimal` , `Single` или `Double` . Это означает, что можно преобразовать `Byte` в любой из этих типов без возникновения <xref:System.OverflowException?displayProperty=nameWithType> ошибки.
  
- **Символы типа.** `Byte` не имеет символа типа литерала или символа типа идентификатора.

- **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Пример

 В следующем примере `b` — это `Byte` переменная. Инструкции демонстрируют диапазон переменных и применение к нему операторов побитового сдвига.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>См. также

- <xref:System.Byte?displayProperty=nameWithType>
- [Типы данных](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Сводка по преобразованию](../keywords/conversion-summary.md)
- [Эффективное использование типов данных](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
