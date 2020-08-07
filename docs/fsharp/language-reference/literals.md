---
title: Литералы
description: 'Сведения о типах литералов на языке программирования F #.'
ms.date: 06/28/2019
ms.openlocfilehash: 98d609a1cf0beb00c0dd4d45ea343aaa2280b62e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855027"
---
# <a name="literals"></a><span data-ttu-id="d5363-103">Литералы</span><span class="sxs-lookup"><span data-stu-id="d5363-103">Literals</span></span>

<span data-ttu-id="d5363-104">В этой статье приводится таблица, в которой показано, как указать тип литерала в F #.</span><span class="sxs-lookup"><span data-stu-id="d5363-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

> [!NOTE]
> <span data-ttu-id="d5363-105">Справочник по API docs.microsoft.com для F # не завершен.</span><span class="sxs-lookup"><span data-stu-id="d5363-105">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="d5363-106">Если вы столкнулись с неработающими ссылками, используйте [документацию по основной библиотеке F #](https://fsharp.github.io/fsharp-core-docs/) .</span><span class="sxs-lookup"><span data-stu-id="d5363-106">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

## <a name="literal-types"></a><span data-ttu-id="d5363-107">Типы литералов</span><span class="sxs-lookup"><span data-stu-id="d5363-107">Literal types</span></span>

<span data-ttu-id="d5363-108">В следующей таблице показаны типы литералов в F #.</span><span class="sxs-lookup"><span data-stu-id="d5363-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="d5363-109">Символы, представляющие цифры в шестнадцатеричном формате, не учитывают регистр; символы, которые определяют тип, учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="d5363-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="d5363-110">Type</span><span class="sxs-lookup"><span data-stu-id="d5363-110">Type</span></span>|<span data-ttu-id="d5363-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="d5363-111">Description</span></span>|<span data-ttu-id="d5363-112">Суффикс или префикс</span><span class="sxs-lookup"><span data-stu-id="d5363-112">Suffix or prefix</span></span>|<span data-ttu-id="d5363-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="d5363-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="d5363-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="d5363-114">sbyte</span></span>|<span data-ttu-id="d5363-115">8-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="d5363-115">signed 8-bit integer</span></span>|<span data-ttu-id="d5363-116">y</span><span class="sxs-lookup"><span data-stu-id="d5363-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="d5363-117">byte</span><span class="sxs-lookup"><span data-stu-id="d5363-117">byte</span></span>|<span data-ttu-id="d5363-118">8-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="d5363-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="d5363-119">Uy</span><span class="sxs-lookup"><span data-stu-id="d5363-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="d5363-120">int16</span><span class="sxs-lookup"><span data-stu-id="d5363-120">int16</span></span>|<span data-ttu-id="d5363-121">16-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="d5363-121">signed 16-bit integer</span></span>|<span data-ttu-id="d5363-122">s</span><span class="sxs-lookup"><span data-stu-id="d5363-122">s</span></span>|`86s`|
|<span data-ttu-id="d5363-123">uint16</span><span class="sxs-lookup"><span data-stu-id="d5363-123">uint16</span></span>|<span data-ttu-id="d5363-124">16-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="d5363-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="d5363-125">us</span><span class="sxs-lookup"><span data-stu-id="d5363-125">us</span></span>|`86us`|
|<span data-ttu-id="d5363-126">int</span><span class="sxs-lookup"><span data-stu-id="d5363-126">int</span></span><br /><br /><span data-ttu-id="d5363-127">int32</span><span class="sxs-lookup"><span data-stu-id="d5363-127">int32</span></span>|<span data-ttu-id="d5363-128">32-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="d5363-128">signed 32-bit integer</span></span>|<span data-ttu-id="d5363-129">l или нет</span><span class="sxs-lookup"><span data-stu-id="d5363-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="d5363-130">uint</span><span class="sxs-lookup"><span data-stu-id="d5363-130">uint</span></span><br /><br /><span data-ttu-id="d5363-131">uint32</span><span class="sxs-lookup"><span data-stu-id="d5363-131">uint32</span></span>|<span data-ttu-id="d5363-132">32-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="d5363-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="d5363-133">u или UL</span><span class="sxs-lookup"><span data-stu-id="d5363-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="d5363-134">нативеинт</span><span class="sxs-lookup"><span data-stu-id="d5363-134">nativeint</span></span>|<span data-ttu-id="d5363-135">собственный указатель на натуральное число со знаком</span><span class="sxs-lookup"><span data-stu-id="d5363-135">native pointer to a signed natural number</span></span>|<span data-ttu-id="d5363-136">n</span><span class="sxs-lookup"><span data-stu-id="d5363-136">n</span></span>|`123n`|
|<span data-ttu-id="d5363-137">unativeint</span><span class="sxs-lookup"><span data-stu-id="d5363-137">unativeint</span></span>|<span data-ttu-id="d5363-138">собственный указатель как беззнаковое натуральное число</span><span class="sxs-lookup"><span data-stu-id="d5363-138">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="d5363-139">понижен</span><span class="sxs-lookup"><span data-stu-id="d5363-139">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="d5363-140">int64</span><span class="sxs-lookup"><span data-stu-id="d5363-140">int64</span></span>|<span data-ttu-id="d5363-141">64-разрядное целое число со знаком</span><span class="sxs-lookup"><span data-stu-id="d5363-141">signed 64-bit integer</span></span>|<span data-ttu-id="d5363-142">L</span><span class="sxs-lookup"><span data-stu-id="d5363-142">L</span></span>|`86L`|
|<span data-ttu-id="d5363-143">uint64</span><span class="sxs-lookup"><span data-stu-id="d5363-143">uint64</span></span>|<span data-ttu-id="d5363-144">64-разрядное натуральное число без знака</span><span class="sxs-lookup"><span data-stu-id="d5363-144">unsigned 64-bit natural number</span></span>|<span data-ttu-id="d5363-145">UL</span><span class="sxs-lookup"><span data-stu-id="d5363-145">UL</span></span>|`86UL`|
|<span data-ttu-id="d5363-146">Single, float32</span><span class="sxs-lookup"><span data-stu-id="d5363-146">single, float32</span></span>|<span data-ttu-id="d5363-147">32-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="d5363-147">32-bit floating point number</span></span>|<span data-ttu-id="d5363-148">F или f</span><span class="sxs-lookup"><span data-stu-id="d5363-148">F or f</span></span>|<span data-ttu-id="d5363-149">`4.14F` или `4.14f`</span><span class="sxs-lookup"><span data-stu-id="d5363-149">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="d5363-150">возврата</span><span class="sxs-lookup"><span data-stu-id="d5363-150">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="d5363-151">сделать Дважды</span><span class="sxs-lookup"><span data-stu-id="d5363-151">float; double</span></span>|<span data-ttu-id="d5363-152">64-разрядное число с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="d5363-152">64-bit floating point number</span></span>|<span data-ttu-id="d5363-153">none</span><span class="sxs-lookup"><span data-stu-id="d5363-153">none</span></span>|<span data-ttu-id="d5363-154">`4.14`, `2.3E+32` или `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="d5363-154">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="d5363-155">ВОЗВРАТА</span><span class="sxs-lookup"><span data-stu-id="d5363-155">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="d5363-156">BIGINT</span><span class="sxs-lookup"><span data-stu-id="d5363-156">bigint</span></span>|<span data-ttu-id="d5363-157">целое число не ограничено 64-разрядным представлением</span><span class="sxs-lookup"><span data-stu-id="d5363-157">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="d5363-158">I</span><span class="sxs-lookup"><span data-stu-id="d5363-158">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="d5363-159">Decimal</span><span class="sxs-lookup"><span data-stu-id="d5363-159">decimal</span></span>|<span data-ttu-id="d5363-160">дробное число, представленное в виде фиксированной точки или рационального числа</span><span class="sxs-lookup"><span data-stu-id="d5363-160">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="d5363-161">M или m</span><span class="sxs-lookup"><span data-stu-id="d5363-161">M or m</span></span>|<span data-ttu-id="d5363-162">`0.7833M` или `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="d5363-162">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="d5363-163">Char</span><span class="sxs-lookup"><span data-stu-id="d5363-163">Char</span></span>|<span data-ttu-id="d5363-164">символьный формат Юникода</span><span class="sxs-lookup"><span data-stu-id="d5363-164">Unicode character</span></span>|<span data-ttu-id="d5363-165">none</span><span class="sxs-lookup"><span data-stu-id="d5363-165">none</span></span>|<span data-ttu-id="d5363-166">`'a'` или `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="d5363-166">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="d5363-167">Строка</span><span class="sxs-lookup"><span data-stu-id="d5363-167">String</span></span>|<span data-ttu-id="d5363-168">Строка Юникода</span><span class="sxs-lookup"><span data-stu-id="d5363-168">Unicode string</span></span>|<span data-ttu-id="d5363-169">none</span><span class="sxs-lookup"><span data-stu-id="d5363-169">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="d5363-170">or</span><span class="sxs-lookup"><span data-stu-id="d5363-170">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="d5363-171">or</span><span class="sxs-lookup"><span data-stu-id="d5363-171">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="d5363-172">or</span><span class="sxs-lookup"><span data-stu-id="d5363-172">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="d5363-173">См. также [строки](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="d5363-173">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="d5363-174">byte</span><span class="sxs-lookup"><span data-stu-id="d5363-174">byte</span></span>|<span data-ttu-id="d5363-175">Символ ASCII</span><span class="sxs-lookup"><span data-stu-id="d5363-175">ASCII character</span></span>|<span data-ttu-id="d5363-176">B</span><span class="sxs-lookup"><span data-stu-id="d5363-176">B</span></span>|`'a'B`|
|<span data-ttu-id="d5363-177">byte[]</span><span class="sxs-lookup"><span data-stu-id="d5363-177">byte[]</span></span>|<span data-ttu-id="d5363-178">строка ASCII</span><span class="sxs-lookup"><span data-stu-id="d5363-178">ASCII string</span></span>|<span data-ttu-id="d5363-179">B</span><span class="sxs-lookup"><span data-stu-id="d5363-179">B</span></span>|`"text"B`|
|<span data-ttu-id="d5363-180">String или Byte []</span><span class="sxs-lookup"><span data-stu-id="d5363-180">String or byte[]</span></span>|<span data-ttu-id="d5363-181">буквальная строка</span><span class="sxs-lookup"><span data-stu-id="d5363-181">verbatim string</span></span>|<span data-ttu-id="d5363-182">префикс @</span><span class="sxs-lookup"><span data-stu-id="d5363-182">@ prefix</span></span>|<span data-ttu-id="d5363-183">`@"\\server\share"`Юникод</span><span class="sxs-lookup"><span data-stu-id="d5363-183">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="d5363-184">`@"\\server\share"B`СИМВОЛ</span><span class="sxs-lookup"><span data-stu-id="d5363-184">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="d5363-185">Именованные литералы</span><span class="sxs-lookup"><span data-stu-id="d5363-185">Named literals</span></span>

<span data-ttu-id="d5363-186">Значения, которые должны быть константами, могут быть помечены атрибутом [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) .</span><span class="sxs-lookup"><span data-stu-id="d5363-186">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="d5363-187">Этот атрибут приводит к тому, что значение компилируется как константа.</span><span class="sxs-lookup"><span data-stu-id="d5363-187">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="d5363-188">В выражениях сопоставления шаблонов идентификаторы, начинающиеся с символов нижнего регистра, всегда обрабатываются как переменные для привязки, а не как литералы, поэтому при определении литералов обычно следует использовать начальные прописные буквы.</span><span class="sxs-lookup"><span data-stu-id="d5363-188">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="d5363-189">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5363-189">Remarks</span></span>

<span data-ttu-id="d5363-190">Строки в Юникоде могут содержать явные кодировки, которые можно указать с помощью, `\u` за которым следует 16-разрядный шестнадцатеричный код (0000-FFFF) или кодировка UTF-32, которую можно указать с помощью, `\U` за которым следует 32-разрядный шестнадцатеричный код, представляющий любую кодовую точку Юникода (00000000-0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="d5363-190">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="d5363-191">Использование других побитовых операторов, кроме `|||` , не допускается.</span><span class="sxs-lookup"><span data-stu-id="d5363-191">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="d5363-192">Целые числа в других базовых базах</span><span class="sxs-lookup"><span data-stu-id="d5363-192">Integers in other bases</span></span>

<span data-ttu-id="d5363-193">32-разрядные целые числа со знаком также могут быть указаны в шестнадцатеричном, восьмеричном или двоичном формате с помощью `0x` `0o` `0b` префикса или соответственно.</span><span class="sxs-lookup"><span data-stu-id="d5363-193">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="d5363-194">Знаки подчеркивания в числовых литералах</span><span class="sxs-lookup"><span data-stu-id="d5363-194">Underscores in numeric literals</span></span>

<span data-ttu-id="d5363-195">Цифры можно разделять символом подчеркивания ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="d5363-195">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="d5363-196">См. также</span><span class="sxs-lookup"><span data-stu-id="d5363-196">See also</span></span>

- [<span data-ttu-id="d5363-197">Класс Core. Литералаттрибуте</span><span class="sxs-lookup"><span data-stu-id="d5363-197">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
