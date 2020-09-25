---
description: Директивы препроцессора C#
title: Директивы препроцессора C#
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 210a024a8062f5070b2a500384f51b37c9d802c0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157958"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="6e684-103">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="6e684-103">C# preprocessor directives</span></span>

<span data-ttu-id="6e684-104">В этом разделе содержатся сведения о следующих директивах препроцессора C#:</span><span class="sxs-lookup"><span data-stu-id="6e684-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="6e684-105">#if</span><span class="sxs-lookup"><span data-stu-id="6e684-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="6e684-106">#else</span><span class="sxs-lookup"><span data-stu-id="6e684-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="6e684-107">#elif</span><span class="sxs-lookup"><span data-stu-id="6e684-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="6e684-108">#endif</span><span class="sxs-lookup"><span data-stu-id="6e684-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="6e684-109">#define</span><span class="sxs-lookup"><span data-stu-id="6e684-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="6e684-110">#undef</span><span class="sxs-lookup"><span data-stu-id="6e684-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="6e684-111">#warning</span><span class="sxs-lookup"><span data-stu-id="6e684-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="6e684-112">#error</span><span class="sxs-lookup"><span data-stu-id="6e684-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="6e684-113">#line</span><span class="sxs-lookup"><span data-stu-id="6e684-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="6e684-114">#region</span><span class="sxs-lookup"><span data-stu-id="6e684-114">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="6e684-115">#endregion</span><span class="sxs-lookup"><span data-stu-id="6e684-115">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="6e684-116">#pragma</span><span class="sxs-lookup"><span data-stu-id="6e684-116">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="6e684-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="6e684-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="6e684-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="6e684-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="6e684-119">Дополнительные сведения и примеры см. в разделах по каждой из этих директив.</span><span class="sxs-lookup"><span data-stu-id="6e684-119">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="6e684-120">Хотя у компилятора нет отдельного препроцессора, директивы, описанные в этом разделе, обрабатываются так, как если бы он был.</span><span class="sxs-lookup"><span data-stu-id="6e684-120">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="6e684-121">Они используются в условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="6e684-121">They are used to help in conditional compilation.</span></span> <span data-ttu-id="6e684-122">В отличие от директив C и C++ вы не можете использовать их для создания макросов.</span><span class="sxs-lookup"><span data-stu-id="6e684-122">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="6e684-123">Директива препроцессора должна быть единственной инструкцией в строке.</span><span class="sxs-lookup"><span data-stu-id="6e684-123">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e684-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6e684-124">See also</span></span>

- [<span data-ttu-id="6e684-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6e684-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6e684-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6e684-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
