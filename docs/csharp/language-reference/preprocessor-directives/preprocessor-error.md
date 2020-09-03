---
description: '#error. Справочник по C#'
title: '#error. Справочник по C#'
ms.date: 08/24/2020
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 76325901c5e39f340545b186a0aa9546cd853ff8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138102"
---
# <a name="error-c-reference"></a><span data-ttu-id="8e0ef-103">#error (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8e0ef-103">#error (C# Reference)</span></span>

<span data-ttu-id="8e0ef-104">`#error` позволяет создать определяемую пользователем ошибку [CS1029](../compiler-messages/cs1029.md) из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="8e0ef-104">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="8e0ef-105">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e0ef-105">For example:</span></span>

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> <span data-ttu-id="8e0ef-106">Компилятор обрабатывает `#error version` особым образом и сообщает об ошибке компилятора CS8304 с сообщением, содержащим используемые версии компилятора и языка.</span><span class="sxs-lookup"><span data-stu-id="8e0ef-106">The compiler treats `#error version` in a special way and reports a compiler error, CS8304, with a message containing the used compiler and language versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e0ef-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e0ef-107">Remarks</span></span>

<span data-ttu-id="8e0ef-108">Как правило, `#error` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="8e0ef-108">A common use of `#error` is in a conditional directive.</span></span>

<span data-ttu-id="8e0ef-109">Кроме того, с помощью директивы [#warning](./preprocessor-warning.md) можно создать определяемое пользователем предупреждение.</span><span class="sxs-lookup"><span data-stu-id="8e0ef-109">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>

## <a name="example"></a><span data-ttu-id="8e0ef-110">Пример</span><span class="sxs-lookup"><span data-stu-id="8e0ef-110">Example</span></span>

```csharp
// preprocessor_error.cs
// CS1029 expected
#define DEBUG
class MainClass
{
    static void Main()
    {
#if DEBUG
#error DEBUG is defined
#endif
    }
}
```

## <a name="see-also"></a><span data-ttu-id="8e0ef-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8e0ef-111">See also</span></span>

- [<span data-ttu-id="8e0ef-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8e0ef-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8e0ef-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8e0ef-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8e0ef-114">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="8e0ef-114">C# Preprocessor Directives</span></span>](./index.md)
