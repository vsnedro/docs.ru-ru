---
description: Ссылочные типы. Справочник по C#
title: Ссылочные типы. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 1a9df3c95d6f5052821be8db5ecf5a8ed99a8ba7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137062"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="37ede-103">Ссылочные типы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="37ede-103">Reference types (C# Reference)</span></span>

<span data-ttu-id="37ede-104">В C# существуют две разновидности типов: ссылочные типы и типы значений.</span><span class="sxs-lookup"><span data-stu-id="37ede-104">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="37ede-105">В переменных ссылочных типов хранятся ссылки на их данные (объекты), а переменные типа значений содержат свои данные непосредственно.</span><span class="sxs-lookup"><span data-stu-id="37ede-105">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="37ede-106">Две переменные ссылочного типа могут ссылаться на один и тот же объект, поэтому операции над одной переменной могут затрагивать объект, на который ссылается другая переменная.</span><span class="sxs-lookup"><span data-stu-id="37ede-106">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="37ede-107">Каждая переменная типа значения имеет собственную копию данных, и операции над одной переменной не могут затрагивать другую (за исключением переменных параметров in, ref и out; см. описание модификатора параметров [in](in-parameter-modifier.md), [ref](ref.md) и [out](out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="37ede-107">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](in-parameter-modifier.md), [ref](ref.md) and [out](out-parameter-modifier.md) parameter modifier).</span></span>

 <span data-ttu-id="37ede-108">Для объявления ссылочных типов используются следующие ключевые слова:</span><span class="sxs-lookup"><span data-stu-id="37ede-108">The following keywords are used to declare reference types:</span></span>

- [<span data-ttu-id="37ede-109">class</span><span class="sxs-lookup"><span data-stu-id="37ede-109">class</span></span>](class.md)

- [<span data-ttu-id="37ede-110">interface</span><span class="sxs-lookup"><span data-stu-id="37ede-110">interface</span></span>](interface.md)

- [<span data-ttu-id="37ede-111">delegate</span><span class="sxs-lookup"><span data-stu-id="37ede-111">delegate</span></span>](../builtin-types/reference-types.md)

 <span data-ttu-id="37ede-112">В C# также предусмотрены следующие встроенные ссылочные типы:</span><span class="sxs-lookup"><span data-stu-id="37ede-112">C# also provides the following built-in reference types:</span></span>

- [<span data-ttu-id="37ede-113">dynamic</span><span class="sxs-lookup"><span data-stu-id="37ede-113">dynamic</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="37ede-114">object</span><span class="sxs-lookup"><span data-stu-id="37ede-114">object</span></span>](../builtin-types/reference-types.md)

- [<span data-ttu-id="37ede-115">string</span><span class="sxs-lookup"><span data-stu-id="37ede-115">string</span></span>](../builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="37ede-116">См. также</span><span class="sxs-lookup"><span data-stu-id="37ede-116">See also</span></span>

- [<span data-ttu-id="37ede-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="37ede-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="37ede-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="37ede-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="37ede-119">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="37ede-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="37ede-120">Типы значений</span><span class="sxs-lookup"><span data-stu-id="37ede-120">Value types</span></span>](../builtin-types/value-types.md)
