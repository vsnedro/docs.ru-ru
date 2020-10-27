---
description: Сведения о встроенном типе символов в C#
title: Тип char. Справочник по C#
ms.date: 05/11/2020
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1cb40759b81a1fcedcf5962b57d79cf3a64df561
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471880"
---
# <a name="char-c-reference"></a><span data-ttu-id="9a7f0-103">char (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9a7f0-103">char (C# reference)</span></span>

<span data-ttu-id="9a7f0-104">Ключевое слово типа `char` — это псевдоним для типа структуры <xref:System.Char?displayProperty=nameWithType> .NET, представляющий символ UTF-16 в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-104">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="9a7f0-105">Type</span><span class="sxs-lookup"><span data-stu-id="9a7f0-105">Type</span></span>|<span data-ttu-id="9a7f0-106">Диапазон</span><span class="sxs-lookup"><span data-stu-id="9a7f0-106">Range</span></span>|<span data-ttu-id="9a7f0-107">Размер</span><span class="sxs-lookup"><span data-stu-id="9a7f0-107">Size</span></span>|<span data-ttu-id="9a7f0-108">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="9a7f0-108">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="9a7f0-109">От U+0000 до U+FFFF</span><span class="sxs-lookup"><span data-stu-id="9a7f0-109">U+0000 to U+FFFF</span></span>|<span data-ttu-id="9a7f0-110">16 разрядов</span><span class="sxs-lookup"><span data-stu-id="9a7f0-110">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="9a7f0-111">Значение по умолчанию для типа `char` — `\0`, то есть U+0000.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-111">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="9a7f0-112">Тип `char` поддерживает [сравнение](../operators/comparison-operators.md), [проверку равенства](../operators/equality-operators.md), а также операции [инкремента](../operators/arithmetic-operators.md#increment-operator-) и [декремента](../operators/arithmetic-operators.md#decrement-operator---).</span><span class="sxs-lookup"><span data-stu-id="9a7f0-112">The `char` type supports [comparison](../operators/comparison-operators.md), [equality](../operators/equality-operators.md), [increment](../operators/arithmetic-operators.md#increment-operator-), and [decrement](../operators/arithmetic-operators.md#decrement-operator---) operators.</span></span> <span data-ttu-id="9a7f0-113">Кроме того, для операндов `char` [арифметические](../operators/arithmetic-operators.md) и [побитовые логические](../operators/bitwise-and-shift-operators.md) операторы выполняют операцию с соответствующими кодами символов и создают результат типа `int`.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-113">Moreover, for `char` operands, [arithmetic](../operators/arithmetic-operators.md) and [bitwise logical](../operators/bitwise-and-shift-operators.md) operators perform an operation on the corresponding character codes and produce the result of the `int` type.</span></span>

<span data-ttu-id="9a7f0-114">Тип [string](reference-types.md#the-string-type) представляет текст как последовательность значений `char`.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-114">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="9a7f0-115">Литералы</span><span class="sxs-lookup"><span data-stu-id="9a7f0-115">Literals</span></span>

<span data-ttu-id="9a7f0-116">Значение `char` можно указать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a7f0-116">You can specify a `char` value with:</span></span>

- <span data-ttu-id="9a7f0-117">символьный литерал;</span><span class="sxs-lookup"><span data-stu-id="9a7f0-117">a character literal.</span></span>
- <span data-ttu-id="9a7f0-118">escape-последовательность Юникода, то есть символы `\u`, за которыми следует шестнадцатеричное представление кода символа из четырех символов;</span><span class="sxs-lookup"><span data-stu-id="9a7f0-118">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="9a7f0-119">шестнадцатеричная escape-последовательность, то есть символы `\x`, за которыми следует шестнадцатеричное представление кода символа.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-119">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](snippets/shared/CharType.cs#Literals)]

<span data-ttu-id="9a7f0-120">Как показано в предыдущем примере, можно также привести значение кода символа к соответствующему значению `char`.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-120">As the preceding example shows, you can also cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="9a7f0-121">В случае escape-последовательности Юникода необходимо указать все четыре шестнадцатеричные цифры.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-121">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="9a7f0-122">То есть `\u006A` — допустимая escape-последовательность, а `\u06A` и `\u6A` нет.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-122">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="9a7f0-123">В случае шестнадцатеричной escape-последовательности начальные нули можно опустить.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-123">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="9a7f0-124">То есть `\x006A`, `\x06A` и `\x6A` — допустимые escape-последовательности, соответствующие одному символу.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-124">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="9a7f0-125">Преобразования</span><span class="sxs-lookup"><span data-stu-id="9a7f0-125">Conversions</span></span>

<span data-ttu-id="9a7f0-126">Тип `char` неявно преобразуется в следующие [целочисленные](integral-numeric-types.md) типы: `ushort`, `int`, `uint`, `long` и `ulong`.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-126">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="9a7f0-127">Он также может быть неявно преобразован во встроенные числовые типы [с плавающей запятой](floating-point-numeric-types.md): `float`, `double` и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-127">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="9a7f0-128">Он явно преобразуется в целочисленные типы `sbyte`, `byte` и `short`.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-128">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="9a7f0-129">Неявные преобразования из других типов в тип `char` не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-129">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="9a7f0-130">Но любой [целочисленный тип](integral-numeric-types.md) или числовой тип [с плавающей запятой](floating-point-numeric-types.md) явно преобразуется в `char`.</span><span class="sxs-lookup"><span data-stu-id="9a7f0-130">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9a7f0-131">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9a7f0-131">C# language specification</span></span>

<span data-ttu-id="9a7f0-132">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="9a7f0-132">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9a7f0-133">См. также</span><span class="sxs-lookup"><span data-stu-id="9a7f0-133">See also</span></span>

- [<span data-ttu-id="9a7f0-134">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9a7f0-134">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9a7f0-135">Типы значений</span><span class="sxs-lookup"><span data-stu-id="9a7f0-135">Value types</span></span>](value-types.md)
- [<span data-ttu-id="9a7f0-136">Строки</span><span class="sxs-lookup"><span data-stu-id="9a7f0-136">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [<span data-ttu-id="9a7f0-137">Кодировка символов в .NET</span><span class="sxs-lookup"><span data-stu-id="9a7f0-137">Character encoding in .NET</span></span>](../../../standard/base-types/character-encoding-introduction.md)
