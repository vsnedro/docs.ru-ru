---
title: Руководство по программированию на C#. Небезопасный код и указатели
Description: Сведения о небезопасном коде и указателях. C# не поддерживает указатели, однако позволяет с помощью ключевого слова unsafe задать небезопасный контекст, в котором использование указателей возможно.
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 5684a97ed6f7b6632d8fe3d52747d9187c4b8cbc
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381779"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="b749f-104">Руководство по программированию на C#. Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="b749f-104">Unsafe code and pointers (C# Programming Guide)</span></span>

<span data-ttu-id="b749f-105">Для обеспечения типобезопасности и безопасности язык C# по умолчанию не поддерживает арифметику указателей.</span><span class="sxs-lookup"><span data-stu-id="b749f-105">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="b749f-106">Но ключевое слово [unsafe](../../language-reference/keywords/unsafe.md) позволяет задать небезопасный контекст, в котором использование указателей возможно.</span><span class="sxs-lookup"><span data-stu-id="b749f-106">However, by using the [unsafe](../../language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="b749f-107">Дополнительные сведения об указателях см. в разделе [Типы указателей (Руководство по программированию на C#)](pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="b749f-107">For more information about pointers, see [Pointer types](pointer-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b749f-108">В общеязыковой среде выполнения (CLR) небезопасный код называется непроверяемым.</span><span class="sxs-lookup"><span data-stu-id="b749f-108">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="b749f-109">Небезопасный код в C# не обязательно опасен, просто его безопасность нельзя проверить в CLR.</span><span class="sxs-lookup"><span data-stu-id="b749f-109">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="b749f-110">Поэтому CLR будет выполнять небезопасный код, только если он находится в полностью доверенной сборке.</span><span class="sxs-lookup"><span data-stu-id="b749f-110">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="b749f-111">Если вы используете небезопасный код, вы сами несете ответственность за возможные риски безопасности и ошибки указателей.</span><span class="sxs-lookup"><span data-stu-id="b749f-111">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="b749f-112">Общие сведения о небезопасном коде</span><span class="sxs-lookup"><span data-stu-id="b749f-112">Unsafe code overview</span></span>

<span data-ttu-id="b749f-113">Небезопасный код имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="b749f-113">Unsafe code has the following properties:</span></span>

- <span data-ttu-id="b749f-114">Методы, типы и блоки кода можно определить как небезопасные.</span><span class="sxs-lookup"><span data-stu-id="b749f-114">Methods, types, and code blocks can be defined as unsafe.</span></span>

- <span data-ttu-id="b749f-115">В некоторых случаях небезопасный код может увеличить скорость работы приложения, если не проверяются границы массивов.</span><span class="sxs-lookup"><span data-stu-id="b749f-115">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>

- <span data-ttu-id="b749f-116">Небезопасный код необходим при вызове встроенных стандартных функций, требующих указателей.</span><span class="sxs-lookup"><span data-stu-id="b749f-116">Unsafe code is required when you call native functions that require pointers.</span></span>

- <span data-ttu-id="b749f-117">Использование небезопасного кода создает риски для стабильности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="b749f-117">Using unsafe code introduces security and stability risks.</span></span>

- <span data-ttu-id="b749f-118">Код, содержащий небезопасные блоки, должен компилироваться с параметром компилятора [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b749f-118">The code that contains unsafe blocks must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="b749f-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b749f-119">Related sections</span></span>

<span data-ttu-id="b749f-120">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="b749f-120">For more information, see:</span></span>

- [<span data-ttu-id="b749f-121">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="b749f-121">Pointer types</span></span>](pointer-types.md)

- [<span data-ttu-id="b749f-122">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="b749f-122">Fixed size buffers</span></span>](fixed-size-buffers.md)

## <a name="c-language-specification"></a><span data-ttu-id="b749f-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b749f-123">C# language specification</span></span>

<span data-ttu-id="b749f-124">Дополнительные сведения см. в разделе [Небезопасный код](~/_csharplang/spec/unsafe-code.md) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b749f-124">For more information, see the [Unsafe code](~/_csharplang/spec/unsafe-code.md) topic of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b749f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b749f-125">See also</span></span>

- [<span data-ttu-id="b749f-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b749f-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b749f-127">unsafe</span><span class="sxs-lookup"><span data-stu-id="b749f-127">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
