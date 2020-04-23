---
title: Справочник по C#. Встроенные типы
description: Сведения о встроенных типах значений и ссылочных типах C#.
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: bf8823c6674b1ff3f0028a50df8ce8d0f803cfc1
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389493"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="f79b4-103">Встроенные типы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f79b4-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="f79b4-104">В следующей таблице приведены встроенные типы [значений](value-types.md) языка C#:</span><span class="sxs-lookup"><span data-stu-id="f79b4-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="f79b4-105">Ключевое слово типа C#</span><span class="sxs-lookup"><span data-stu-id="f79b4-105">C# type keyword</span></span>|<span data-ttu-id="f79b4-106">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="f79b4-106">.NET type</span></span>|
|--------------|-------------------------|
|[`bool`](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|
|[`byte`](integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|
|[`sbyte`](integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|
|[`char`](char.md)|<xref:System.Char?displayProperty=nameWithType>|
|[`decimal`](floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|
|[`double`](floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|
|[`float`](floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|
|[`int`](integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|
|[`uint`](integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

<span data-ttu-id="f79b4-107">В следующей таблице приведены встроенные [ссылочные](../keywords/reference-types.md) типы языка C#:</span><span class="sxs-lookup"><span data-stu-id="f79b4-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="f79b4-108">Ключевое слово типа C#</span><span class="sxs-lookup"><span data-stu-id="f79b4-108">C# type keyword</span></span>|<span data-ttu-id="f79b4-109">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="f79b4-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

<span data-ttu-id="f79b4-110">В таблицах выше каждое ключевое слово типа C# в левом столбце является псевдонимом для соответствующего типа .NET.</span><span class="sxs-lookup"><span data-stu-id="f79b4-110">In the preceding tables, each C# type keyword from the left column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="f79b4-111">Они взаимозаменяемые.</span><span class="sxs-lookup"><span data-stu-id="f79b4-111">They are interchangeable.</span></span> <span data-ttu-id="f79b4-112">Например, следующие объявления объявляют переменные одного типа:</span><span class="sxs-lookup"><span data-stu-id="f79b4-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="f79b4-113">Ключевое слово [`void`](void.md) представляет отсутствие типа.</span><span class="sxs-lookup"><span data-stu-id="f79b4-113">The [`void`](void.md) keyword represents the absence of a type.</span></span> <span data-ttu-id="f79b4-114">Оно используется в качестве возвращаемого типа метода, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="f79b4-114">You use it as the return type of a method that doesn't return a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="f79b4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f79b4-115">See also</span></span>

- [<span data-ttu-id="f79b4-116">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f79b4-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f79b4-117">Значения по умолчанию типов C#</span><span class="sxs-lookup"><span data-stu-id="f79b4-117">Default values of C# types</span></span>](default-values.md)
- [<span data-ttu-id="f79b4-118">Ключевое слово `dynamic`</span><span class="sxs-lookup"><span data-stu-id="f79b4-118">`dynamic` keyword</span></span>](reference-types.md#the-dynamic-type)
