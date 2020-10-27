---
description: Сведения о ключевом слове void в C#
title: Справочник по C#. void
ms.date: 02/11/2020
f1_keywords:
- void_CSharpKeyword
- void
- (void)
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: fb22fffadeff4db9fcd8e1c8753d44455186aa5a
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471641"
---
# <a name="void-c-reference"></a><span data-ttu-id="ca686-103">Справочник по C#. void</span><span class="sxs-lookup"><span data-stu-id="ca686-103">void (C# reference)</span></span>

<span data-ttu-id="ca686-104">`void` можно использовать в качестве возвращаемого типа [метода](../../programming-guide/classes-and-structs/methods.md) (или [локальной функции](../../programming-guide/classes-and-structs/local-functions.md)) для определения того, что метод не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="ca686-104">You use `void` as the return type of a [method](../../programming-guide/classes-and-structs/methods.md) (or a [local function](../../programming-guide/classes-and-structs/local-functions.md)) to specify that the method doesn't return a value.</span></span>

[!code-csharp[void method](snippets/shared/VoidType.cs#VoidExample)]

<span data-ttu-id="ca686-105">Вы также можете использовать `void` как ссылочный тип для объявления того, что тип указателя неизвестен.</span><span class="sxs-lookup"><span data-stu-id="ca686-105">You can also use `void` as a referent type to declare a pointer to an unknown type.</span></span> <span data-ttu-id="ca686-106">Дополнительные сведения см. в разделе [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="ca686-106">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="ca686-107">Нельзя использовать `void` в качестве типа переменной.</span><span class="sxs-lookup"><span data-stu-id="ca686-107">You cannot use `void` as the type of a variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca686-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ca686-108">See also</span></span>

- [<span data-ttu-id="ca686-109">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ca686-109">C# reference</span></span>](../index.md)
- <xref:System.Void?displayProperty=nameWithType>
