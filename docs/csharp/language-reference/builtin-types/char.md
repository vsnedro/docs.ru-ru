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
# <a name="char-c-reference"></a><span data-ttu-id="5ed4c-102">char (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5ed4c-102">char (C# reference)</span></span>

<span data-ttu-id="5ed4c-103">Ключевое слово типа `char` — это псевдоним для типа структуры <xref:System.Char?displayProperty=nameWithType> .NET, представляющий символ UTF-16 в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="5ed4c-104">Type</span><span class="sxs-lookup"><span data-stu-id="5ed4c-104">Type</span></span>|<span data-ttu-id="5ed4c-105">Диапазон</span><span class="sxs-lookup"><span data-stu-id="5ed4c-105">Range</span></span>|<span data-ttu-id="5ed4c-106">Размер</span><span class="sxs-lookup"><span data-stu-id="5ed4c-106">Size</span></span>|<span data-ttu-id="5ed4c-107">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="5ed4c-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="5ed4c-108">От U+0000 до U+FFFF</span><span class="sxs-lookup"><span data-stu-id="5ed4c-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="5ed4c-109">16 разрядов</span><span class="sxs-lookup"><span data-stu-id="5ed4c-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="5ed4c-110">Значение по умолчанию для типа `char` — `\0`, то есть U+0000.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="5ed4c-111">Тип `char` поддерживает [сравнение](../operators/comparison-operators.md), [проверку равенства](../operators/equality-operators.md), а также операции [инкремента](../operators/arithmetic-operators.md#increment-operator-) и [декремента](../operators/arithmetic-operators.md#decrement-operator---).</span><span class="sxs-lookup"><span data-stu-id="5ed4c-111">The `char` type supports [comparison](../operators/comparison-operators.md), [equality](../operators/equality-operators.md), [increment](../operators/arithmetic-operators.md#increment-operator-), and [decrement](../operators/arithmetic-operators.md#decrement-operator---) operators.</span></span> <span data-ttu-id="5ed4c-112">Кроме того, для операндов `char` [арифметические](../operators/arithmetic-operators.md) и [побитовые логические](../operators/bitwise-and-shift-operators.md) операторы выполняют операцию с соответствующими кодами символов и создают результат типа `int`.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-112">Moreover, for `char` operands, [arithmetic](../operators/arithmetic-operators.md) and [bitwise logical](../operators/bitwise-and-shift-operators.md) operators perform an operation on the corresponding character codes and produce the result of the `int` type.</span></span>

<span data-ttu-id="5ed4c-113">Тип [string](reference-types.md#the-string-type) представляет текст как последовательность значений `char`.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-113">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="5ed4c-114">Литералы</span><span class="sxs-lookup"><span data-stu-id="5ed4c-114">Literals</span></span>

<span data-ttu-id="5ed4c-115">Значение `char` можно указать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5ed4c-115">You can specify a `char` value with:</span></span>

- <span data-ttu-id="5ed4c-116">символьный литерал;</span><span class="sxs-lookup"><span data-stu-id="5ed4c-116">a character literal.</span></span>
- <span data-ttu-id="5ed4c-117">escape-последовательность Юникода, то есть символы `\u`, за которыми следует шестнадцатеричное представление кода символа из четырех символов;</span><span class="sxs-lookup"><span data-stu-id="5ed4c-117">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="5ed4c-118">шестнадцатеричная escape-последовательность, то есть символы `\x`, за которыми следует шестнадцатеричное представление кода символа.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-118">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

<span data-ttu-id="5ed4c-119">Как показано в предыдущем примере, можно также привести значение кода символа к соответствующему значению `char`.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-119">As the preceding example shows, you can also cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="5ed4c-120">В случае escape-последовательности Юникода необходимо указать все четыре шестнадцатеричные цифры.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-120">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="5ed4c-121">То есть `\u006A` — допустимая escape-последовательность, а `\u06A` и `\u6A` нет.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-121">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="5ed4c-122">В случае шестнадцатеричной escape-последовательности начальные нули можно опустить.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-122">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="5ed4c-123">То есть `\x006A`, `\x06A` и `\x6A` — допустимые escape-последовательности, соответствующие одному символу.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-123">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="5ed4c-124">Преобразования</span><span class="sxs-lookup"><span data-stu-id="5ed4c-124">Conversions</span></span>

<span data-ttu-id="5ed4c-125">Тип `char` неявно преобразуется в следующие [целочисленные](integral-numeric-types.md) типы: `ushort`, `int`, `uint`, `long` и `ulong`.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-125">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="5ed4c-126">Он также может быть неявно преобразован во встроенные числовые типы [с плавающей запятой](floating-point-numeric-types.md): `float`, `double` и `decimal`.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-126">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="5ed4c-127">Он явно преобразуется в целочисленные типы `sbyte`, `byte` и `short`.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-127">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="5ed4c-128">Неявные преобразования из других типов в тип `char` не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-128">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="5ed4c-129">Но любой [целочисленный тип](integral-numeric-types.md) или числовой тип [с плавающей запятой](floating-point-numeric-types.md) явно преобразуется в `char`.</span><span class="sxs-lookup"><span data-stu-id="5ed4c-129">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5ed4c-130">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5ed4c-130">C# language specification</span></span>

<span data-ttu-id="5ed4c-131">Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5ed4c-131">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ed4c-132">См. также</span><span class="sxs-lookup"><span data-stu-id="5ed4c-132">See also</span></span>

- [<span data-ttu-id="5ed4c-133">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5ed4c-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5ed4c-134">Типы значений</span><span class="sxs-lookup"><span data-stu-id="5ed4c-134">Value types</span></span>](value-types.md)
- [<span data-ttu-id="5ed4c-135">Строки</span><span class="sxs-lookup"><span data-stu-id="5ed4c-135">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [<span data-ttu-id="5ed4c-136">Кодировка символов в .NET</span><span class="sxs-lookup"><span data-stu-id="5ed4c-136">Character encoding in .NET</span></span>](../../../standard/base-types/character-encoding-introduction.md)
