---
title: Литералы
description: 'Сведения о типах литералов на языке программирования F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 15f73db3c36f7c60ab1eeba96c63a28ebc6d7f01
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559158"
---
# <a name="literals"></a><span data-ttu-id="9f81f-103">Литералы</span><span class="sxs-lookup"><span data-stu-id="9f81f-103">Literals</span></span>

<span data-ttu-id="9f81f-104">В этой статье приводится таблица, в которой показано, как указать тип литерала в F #.</span><span class="sxs-lookup"><span data-stu-id="9f81f-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="9f81f-105">Типы литералов</span><span class="sxs-lookup"><span data-stu-id="9f81f-105">Literal types</span></span>

<span data-ttu-id="9f81f-106">В следующей таблице показаны типы литералов в F #.</span><span class="sxs-lookup"><span data-stu-id="9f81f-106">The following table shows the literal types in F#.</span></span> <span data-ttu-id="9f81f-107">Символы, представляющие цифры в шестнадцатеричном формате, не учитывают регистр; символы, которые определяют тип, учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="9f81f-107">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="9f81f-108">Тип</span><span class="sxs-lookup"><span data-stu-id="9f81f-108">Type</span></span>|<span data-ttu-id="9f81f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9f81f-109">Description</span></span>|<span data-ttu-id="9f81f-110">Суффикс или префикс</span><span class="sxs-lookup"><span data-stu-id="9f81f-110">Suffix or prefix</span></span>|<span data-ttu-id="9f81f-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="9f81f-111">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="9f81f-112">sbyte</span><span class="sxs-lookup"><span data-stu-id="9f81f-112">sbyte</span></span>|<span data-ttu-id="9f81f-113">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="9f81f-113">signed 8-bit integer</span></span>|<span data-ttu-id="9f81f-114">y</span><span class="sxs-lookup"><span data-stu-id="9f81f-114">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="9f81f-115">byte</span><span class="sxs-lookup"><span data-stu-id="9f81f-115">byte</span></span>|<span data-ttu-id="9f81f-116">8-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="9f81f-116">unsigned 8-bit natural number</span></span>|<span data-ttu-id="9f81f-117">Uy</span><span class="sxs-lookup"><span data-stu-id="9f81f-117">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="9f81f-118">int16</span><span class="sxs-lookup"><span data-stu-id="9f81f-118">int16</span></span>|<span data-ttu-id="9f81f-119">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="9f81f-119">signed 16-bit integer</span></span>|<span data-ttu-id="9f81f-120">s</span><span class="sxs-lookup"><span data-stu-id="9f81f-120">s</span></span>|`86s`|
|<span data-ttu-id="9f81f-121">uint16</span><span class="sxs-lookup"><span data-stu-id="9f81f-121">uint16</span></span>|<span data-ttu-id="9f81f-122">16-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="9f81f-122">unsigned 16-bit natural number</span></span>|<span data-ttu-id="9f81f-123">us</span><span class="sxs-lookup"><span data-stu-id="9f81f-123">us</span></span>|`86us`|
|<span data-ttu-id="9f81f-124">INT</span><span class="sxs-lookup"><span data-stu-id="9f81f-124">int</span></span><br /><br /><span data-ttu-id="9f81f-125">int32</span><span class="sxs-lookup"><span data-stu-id="9f81f-125">int32</span></span>|<span data-ttu-id="9f81f-126">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="9f81f-126">signed 32-bit integer</span></span>|<span data-ttu-id="9f81f-127">l или нет</span><span class="sxs-lookup"><span data-stu-id="9f81f-127">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="9f81f-128">uint</span><span class="sxs-lookup"><span data-stu-id="9f81f-128">uint</span></span><br /><br /><span data-ttu-id="9f81f-129">uint32</span><span class="sxs-lookup"><span data-stu-id="9f81f-129">uint32</span></span>|<span data-ttu-id="9f81f-130">32-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="9f81f-130">unsigned 32-bit natural number</span></span>|<span data-ttu-id="9f81f-131">u или UL</span><span class="sxs-lookup"><span data-stu-id="9f81f-131">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="9f81f-132">нативеинт</span><span class="sxs-lookup"><span data-stu-id="9f81f-132">nativeint</span></span>|<span data-ttu-id="9f81f-133">собственный указатель на натуральное число со знаком</span><span class="sxs-lookup"><span data-stu-id="9f81f-133">native pointer to a signed natural number</span></span>|<span data-ttu-id="9f81f-134">n</span><span class="sxs-lookup"><span data-stu-id="9f81f-134">n</span></span>|`123n`|
|<span data-ttu-id="9f81f-135">unativeint</span><span class="sxs-lookup"><span data-stu-id="9f81f-135">unativeint</span></span>|<span data-ttu-id="9f81f-136">собственный указатель как беззнаковое натуральное число</span><span class="sxs-lookup"><span data-stu-id="9f81f-136">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="9f81f-137">понижен</span><span class="sxs-lookup"><span data-stu-id="9f81f-137">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="9f81f-138">int64</span><span class="sxs-lookup"><span data-stu-id="9f81f-138">int64</span></span>|<span data-ttu-id="9f81f-139">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="9f81f-139">signed 64-bit integer</span></span>|<span data-ttu-id="9f81f-140">L</span><span class="sxs-lookup"><span data-stu-id="9f81f-140">L</span></span>|`86L`|
|<span data-ttu-id="9f81f-141">uint64</span><span class="sxs-lookup"><span data-stu-id="9f81f-141">uint64</span></span>|<span data-ttu-id="9f81f-142">64-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="9f81f-142">unsigned 64-bit natural number</span></span>|<span data-ttu-id="9f81f-143">UL</span><span class="sxs-lookup"><span data-stu-id="9f81f-143">UL</span></span>|`86UL`|
|<span data-ttu-id="9f81f-144">Single, float32</span><span class="sxs-lookup"><span data-stu-id="9f81f-144">single, float32</span></span>|<span data-ttu-id="9f81f-145">32-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9f81f-145">32-bit floating point number</span></span>|<span data-ttu-id="9f81f-146">F или f</span><span class="sxs-lookup"><span data-stu-id="9f81f-146">F or f</span></span>|<span data-ttu-id="9f81f-147">`4.14F` либо `4.14f`</span><span class="sxs-lookup"><span data-stu-id="9f81f-147">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="9f81f-148">возврата</span><span class="sxs-lookup"><span data-stu-id="9f81f-148">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="9f81f-149">сделать Дважды</span><span class="sxs-lookup"><span data-stu-id="9f81f-149">float; double</span></span>|<span data-ttu-id="9f81f-150">64-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="9f81f-150">64-bit floating point number</span></span>|<span data-ttu-id="9f81f-151">нет</span><span class="sxs-lookup"><span data-stu-id="9f81f-151">none</span></span>|<span data-ttu-id="9f81f-152">`4.14`, `2.3E+32` или `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="9f81f-152">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="9f81f-153">ВОЗВРАТА</span><span class="sxs-lookup"><span data-stu-id="9f81f-153">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="9f81f-154">BIGINT</span><span class="sxs-lookup"><span data-stu-id="9f81f-154">bigint</span></span>|<span data-ttu-id="9f81f-155">целое число не ограничено 64-разрядным представлением</span><span class="sxs-lookup"><span data-stu-id="9f81f-155">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="9f81f-156">I</span><span class="sxs-lookup"><span data-stu-id="9f81f-156">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="9f81f-157">Decimal</span><span class="sxs-lookup"><span data-stu-id="9f81f-157">decimal</span></span>|<span data-ttu-id="9f81f-158">дробное число, представленное в виде фиксированной точки или рационального числа</span><span class="sxs-lookup"><span data-stu-id="9f81f-158">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="9f81f-159">M или m</span><span class="sxs-lookup"><span data-stu-id="9f81f-159">M or m</span></span>|<span data-ttu-id="9f81f-160">`0.7833M` либо `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="9f81f-160">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="9f81f-161">Char</span><span class="sxs-lookup"><span data-stu-id="9f81f-161">Char</span></span>|<span data-ttu-id="9f81f-162">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="9f81f-162">Unicode character</span></span>|<span data-ttu-id="9f81f-163">нет</span><span class="sxs-lookup"><span data-stu-id="9f81f-163">none</span></span>|<span data-ttu-id="9f81f-164">`'a'` либо `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="9f81f-164">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="9f81f-165">Строка</span><span class="sxs-lookup"><span data-stu-id="9f81f-165">String</span></span>|<span data-ttu-id="9f81f-166">Строка Юникода</span><span class="sxs-lookup"><span data-stu-id="9f81f-166">Unicode string</span></span>|<span data-ttu-id="9f81f-167">нет</span><span class="sxs-lookup"><span data-stu-id="9f81f-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="9f81f-168">или</span><span class="sxs-lookup"><span data-stu-id="9f81f-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="9f81f-169">или</span><span class="sxs-lookup"><span data-stu-id="9f81f-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="9f81f-170">или</span><span class="sxs-lookup"><span data-stu-id="9f81f-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="9f81f-171">См. также [строки](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="9f81f-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="9f81f-172">byte</span><span class="sxs-lookup"><span data-stu-id="9f81f-172">byte</span></span>|<span data-ttu-id="9f81f-173">Символ ASCII</span><span class="sxs-lookup"><span data-stu-id="9f81f-173">ASCII character</span></span>|<span data-ttu-id="9f81f-174">B</span><span class="sxs-lookup"><span data-stu-id="9f81f-174">B</span></span>|`'a'B`|
|<span data-ttu-id="9f81f-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="9f81f-175">byte[]</span></span>|<span data-ttu-id="9f81f-176">строка ASCII</span><span class="sxs-lookup"><span data-stu-id="9f81f-176">ASCII string</span></span>|<span data-ttu-id="9f81f-177">B</span><span class="sxs-lookup"><span data-stu-id="9f81f-177">B</span></span>|`"text"B`|
|<span data-ttu-id="9f81f-178">String или Byte []</span><span class="sxs-lookup"><span data-stu-id="9f81f-178">String or byte[]</span></span>|<span data-ttu-id="9f81f-179">буквальная строка</span><span class="sxs-lookup"><span data-stu-id="9f81f-179">verbatim string</span></span>|<span data-ttu-id="9f81f-180">префикс @</span><span class="sxs-lookup"><span data-stu-id="9f81f-180">@ prefix</span></span>|<span data-ttu-id="9f81f-181">`@"\\server\share"` Юникод</span><span class="sxs-lookup"><span data-stu-id="9f81f-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="9f81f-182">`@"\\server\share"B` СИМВОЛ</span><span class="sxs-lookup"><span data-stu-id="9f81f-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="9f81f-183">Именованные литералы</span><span class="sxs-lookup"><span data-stu-id="9f81f-183">Named literals</span></span>

<span data-ttu-id="9f81f-184">Значения, которые должны быть константами, могут быть помечены атрибутом [Literal](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) .</span><span class="sxs-lookup"><span data-stu-id="9f81f-184">Values that are intended to be constants can be marked with the [Literal](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) attribute.</span></span> <span data-ttu-id="9f81f-185">Этот атрибут приводит к тому, что значение компилируется как константа.</span><span class="sxs-lookup"><span data-stu-id="9f81f-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="9f81f-186">В выражениях сопоставления шаблонов идентификаторы, начинающиеся с символов нижнего регистра, всегда обрабатываются как переменные для привязки, а не как литералы, поэтому при определении литералов обычно следует использовать начальные прописные буквы.</span><span class="sxs-lookup"><span data-stu-id="9f81f-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a><span data-ttu-id="9f81f-187">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f81f-187">Remarks</span></span>

<span data-ttu-id="9f81f-188">Строки в Юникоде могут содержать явные кодировки, которые можно указать с помощью, `\u` за которым следует 16-разрядный шестнадцатеричный код (0000-FFFF) или кодировка UTF-32, которую можно указать с помощью, `\U` за которым следует 32-разрядный шестнадцатеричный код, представляющий любую кодовую точку Юникода (00000000-0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="9f81f-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="9f81f-189">Использование других побитовых операторов, кроме `|||` , не допускается.</span><span class="sxs-lookup"><span data-stu-id="9f81f-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="9f81f-190">Целые числа в других базовых базах</span><span class="sxs-lookup"><span data-stu-id="9f81f-190">Integers in other bases</span></span>

<span data-ttu-id="9f81f-191">32-разрядные целые числа со знаком также могут быть указаны в шестнадцатеричном, восьмеричном или двоичном формате с помощью `0x` `0o` `0b` префикса или соответственно.</span><span class="sxs-lookup"><span data-stu-id="9f81f-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="9f81f-192">Знаки подчеркивания в числовых литералах</span><span class="sxs-lookup"><span data-stu-id="9f81f-192">Underscores in numeric literals</span></span>

<span data-ttu-id="9f81f-193">Цифры можно разделять символом подчеркивания ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="9f81f-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```
