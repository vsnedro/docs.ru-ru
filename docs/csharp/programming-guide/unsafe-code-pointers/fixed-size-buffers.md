---
title: Руководство по программированию на C#. Буферы фиксированного размера
description: Сведения о буферах фиксированного размера. Буферы фиксированного размера используются при написании методов, взаимодействующих с источниками данных, которые созданы на других языках.
ms.date: 04/23/2020
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 1d4f5068121cdc98976954f2d99f4ac020c3b2a8
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381246"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="7c0e1-104">Буферы фиксированного размера (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="7c0e1-104">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="7c0e1-105">В языке C# для создания буфера с массивом фиксированного размера в структуре данных можно использовать оператор [fixed](../../language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7c0e1-105">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="7c0e1-106">Буферы фиксированного размера полезны при написании методов, взаимодействующих с источниками данных, созданными на других языках или платформах.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-106">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="7c0e1-107">Фиксированный массив может принимать любые атрибуты или модификаторы, допустимые для обычных членов структуры.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-107">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="7c0e1-108">Единственным ограничением является то, что массив должен иметь тип `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` или `double`.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-108">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="7c0e1-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c0e1-109">Remarks</span></span>

<span data-ttu-id="7c0e1-110">В безопасном коде структура C#, содержащая массив, не содержит элементы массива.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-110">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="7c0e1-111">Вместо этого в ней присутствуют ссылки на элементы.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-111">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="7c0e1-112">Вы можете внедрить массив фиксированного размера в [структуру](../../language-reference/builtin-types/struct.md), если он используется в блоке [небезопасного](../../language-reference/keywords/unsafe.md) кода.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-112">You can embed an array of fixed size in a [struct](../../language-reference/builtin-types/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="7c0e1-113">Размер следующего объекта `struct` не зависит от количества элементов в массиве, поскольку `pathName` представляет собой ссылку:</span><span class="sxs-lookup"><span data-stu-id="7c0e1-113">Size of the following `struct` doesn't depend on the number of elements in the array, since `pathName` is a reference:</span></span>

[!code-csharp[Struct with embedded array](snippets/FixedKeywordExamples.cs#6)]

<span data-ttu-id="7c0e1-114">`struct` может содержать внедренный массив в небезопасном коде.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-114">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="7c0e1-115">В приведенном ниже примере массив `fixedBuffer` имеет фиксированный размер.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-115">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="7c0e1-116">Для установки указателя на первый элемент используется оператор `fixed`.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-116">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="7c0e1-117">С помощью этого указателя осуществляется доступ к элементам массива.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-117">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="7c0e1-118">Оператор `fixed` закрепляет поле экземпляра `fixedBuffer` в определенном месте в памяти.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-118">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#7)]

<span data-ttu-id="7c0e1-119">Размер массива из 128 элементов `char` составляет 256 байт.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-119">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="7c0e1-120">В буферах типа [char](../../language-reference/builtin-types/char.md) фиксированного размера на один символ всегда приходится два байта независимо от кодировки.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-120">Fixed size [char](../../language-reference/builtin-types/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="7c0e1-121">Это справедливо даже в том случае, когда буферы char маршалируются в методы API или структуры с `CharSet = CharSet.Auto` или `CharSet = CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-121">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="7c0e1-122">Для получения дополнительной информации см. <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-122">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="7c0e1-123">В предыдущем примере демонстрировался доступ к полям `fixed` без закрепления в памяти, доступный в C#, начиная с версии 7.3.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-123">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="7c0e1-124">Еще одним распространенным массивом фиксированного размера является массив [bool](../../language-reference/builtin-types/bool.md).</span><span class="sxs-lookup"><span data-stu-id="7c0e1-124">Another common fixed-size array is the [bool](../../language-reference/builtin-types/bool.md) array.</span></span> <span data-ttu-id="7c0e1-125">Элементы в массиве `bool` всегда имеют размер в один байт.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-125">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="7c0e1-126">Массивы `bool` не подходят для создания битовых массивов или буферов.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-126">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

<span data-ttu-id="7c0e1-127">Буферы фиксированного размера компилируются с помощью класса <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, что указывает среде CLR, что тип содержит неуправляемый массив, который может привести к переполнению.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-127">Fixed size buffers are compiled with the <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, which instructs the common language runtime (CLR) that a type contains an unmanaged array that can potentially overflow.</span></span> <span data-ttu-id="7c0e1-128">Это похоже на память, созданную с помощью [stackalloc](../../language-reference/operators/stackalloc.md), которая автоматически включает функции обнаружения переполнения буфера в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-128">This is similar to memory created using [stackalloc](../../language-reference/operators/stackalloc.md), which automatically enables buffer overrun detection features in the CLR.</span></span> <span data-ttu-id="7c0e1-129">В предыдущем примере показано существование буфера фиксированного размера в `unsafe struct`.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-129">The previous example shows how a fixed size buffer could exist in an `unsafe struct`.</span></span>

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

<span data-ttu-id="7c0e1-130">Созданный компилятором код C# для `Buffer` помечен с помощью атрибутов, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-130">The compiler generated C# for `Buffer`, is attributed as follows:</span></span>

```csharp
internal struct Buffer
{
    [StructLayout(LayoutKind.Sequential, Size = 256)]
    [CompilerGenerated]
    [UnsafeValueType]
    public struct <fixedBuffer>e__FixedBuffer
    {
        public char FixedElementField;
    }

    [FixedBuffer(typeof(char), 128)]
    public <fixedBuffer>e__FixedBuffer fixedBuffer;
}
```

<span data-ttu-id="7c0e1-131">Буферы фиксированного размера отличаются от обычных массивов указанными ниже особенностями.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-131">Fixed size buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="7c0e1-132">Могут использоваться только в [небезопасном](../../language-reference/keywords/unsafe.md) контексте.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-132">May only be used in an [unsafe](../../language-reference/keywords/unsafe.md) context.</span></span>
- <span data-ttu-id="7c0e1-133">Могут быть только полями экземпляров структур.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-133">May only be instance fields of structs.</span></span>
- <span data-ttu-id="7c0e1-134">Всегда являются векторами или одномерными массивами.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-134">They're always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="7c0e1-135">Объявление должно включать длину, например `fixed char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-135">The declaration should include the length, such as `fixed char id[8]`.</span></span> <span data-ttu-id="7c0e1-136">Использовать `fixed char id[]` нельзя.</span><span class="sxs-lookup"><span data-stu-id="7c0e1-136">You cannot use `fixed char id[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c0e1-137">См. также</span><span class="sxs-lookup"><span data-stu-id="7c0e1-137">See also</span></span>

- [<span data-ttu-id="7c0e1-138">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7c0e1-138">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7c0e1-139">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="7c0e1-139">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="7c0e1-140">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="7c0e1-140">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="7c0e1-141">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="7c0e1-141">Interoperability</span></span>](../interop/index.md)
