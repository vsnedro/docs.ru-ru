---
title: Тип char. Справочник по C#
ms.date: 05/11/2020
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: f771626e9777deab30e798559d847615d6124e6d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205778"
---
# <a name="char-c-reference"></a>char (Справочник по C#)

Ключевое слово типа `char` — это псевдоним для типа структуры <xref:System.Char?displayProperty=nameWithType> .NET, представляющий символ UTF-16 в Юникоде.

|Type|Диапазон|Размер|Тип .NET|
|----------|-----------|----------|-------------------------|
|`char`|От U+0000 до U+FFFF|16 разрядов|<xref:System.Char?displayProperty=nameWithType>|

Значение по умолчанию для типа `char` — `\0`, то есть U+0000.

Тип `char` поддерживает [сравнение](../operators/comparison-operators.md), [проверку равенства](../operators/equality-operators.md), а также операции [инкремента](../operators/arithmetic-operators.md#increment-operator-) и [декремента](../operators/arithmetic-operators.md#decrement-operator---). Кроме того, для операндов `char` [арифметические](../operators/arithmetic-operators.md) и [побитовые логические](../operators/bitwise-and-shift-operators.md) операторы выполняют операцию с соответствующими кодами символов и создают результат типа `int`.

Тип [string](reference-types.md#the-string-type) представляет текст как последовательность значений `char`.

## <a name="literals"></a>Литералы

Значение `char` можно указать следующим образом:

- символьный литерал;
- escape-последовательность Юникода, то есть символы `\u`, за которыми следует шестнадцатеричное представление кода символа из четырех символов;
- шестнадцатеричная escape-последовательность, то есть символы `\x`, за которыми следует шестнадцатеричное представление кода символа.

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

Как показано в предыдущем примере, можно также привести значение кода символа к соответствующему значению `char`.

> [!NOTE]
> В случае escape-последовательности Юникода необходимо указать все четыре шестнадцатеричные цифры. То есть `\u006A` — допустимая escape-последовательность, а `\u06A` и `\u6A` нет.
>
> В случае шестнадцатеричной escape-последовательности начальные нули можно опустить. То есть `\x006A`, `\x06A` и `\x6A` — допустимые escape-последовательности, соответствующие одному символу.

## <a name="conversions"></a>Преобразования

Тип `char` неявно преобразуется в следующие [целочисленные](integral-numeric-types.md) типы: `ushort`, `int`, `uint`, `long` и `ulong`. Он также может быть неявно преобразован во встроенные числовые типы [с плавающей запятой](floating-point-numeric-types.md): `float`, `double` и `decimal`. Он явно преобразуется в целочисленные типы `sbyte`, `byte` и `short`.

Неявные преобразования из других типов в тип `char` не предусмотрены. Но любой [целочисленный тип](integral-numeric-types.md) или числовой тип [с плавающей запятой](floating-point-numeric-types.md) явно преобразуется в `char`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Типы значений](value-types.md)
- [Строки](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [Кодировка символов в .NET](../../../standard/base-types/character-encoding-introduction.md)
