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
ms.openlocfilehash: 1269522b2687b76292f7b796a4ffc8095f23442e
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099065"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="ad949-103">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="ad949-103">C# preprocessor directives</span></span>

<span data-ttu-id="ad949-104">В этом разделе содержатся сведения о следующих директивах препроцессора C#:</span><span class="sxs-lookup"><span data-stu-id="ad949-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="ad949-105">#if</span><span class="sxs-lookup"><span data-stu-id="ad949-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="ad949-106">#else</span><span class="sxs-lookup"><span data-stu-id="ad949-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="ad949-107">#elif</span><span class="sxs-lookup"><span data-stu-id="ad949-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="ad949-108">#endif</span><span class="sxs-lookup"><span data-stu-id="ad949-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="ad949-109">#define</span><span class="sxs-lookup"><span data-stu-id="ad949-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="ad949-110">#undef</span><span class="sxs-lookup"><span data-stu-id="ad949-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="ad949-111">#warning</span><span class="sxs-lookup"><span data-stu-id="ad949-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="ad949-112">#error</span><span class="sxs-lookup"><span data-stu-id="ad949-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="ad949-113">#line</span><span class="sxs-lookup"><span data-stu-id="ad949-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="ad949-114">#nullable</span><span class="sxs-lookup"><span data-stu-id="ad949-114">#nullable</span></span>](./preprocessor-nullable.md)
- [<span data-ttu-id="ad949-115">#region</span><span class="sxs-lookup"><span data-stu-id="ad949-115">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="ad949-116">#endregion</span><span class="sxs-lookup"><span data-stu-id="ad949-116">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="ad949-117">#pragma</span><span class="sxs-lookup"><span data-stu-id="ad949-117">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="ad949-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="ad949-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="ad949-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="ad949-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="ad949-120">Дополнительные сведения и примеры см. в разделах по каждой из этих директив.</span><span class="sxs-lookup"><span data-stu-id="ad949-120">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="ad949-121">Хотя у компилятора нет отдельного препроцессора, директивы, описанные в этом разделе, обрабатываются так, как если бы он был.</span><span class="sxs-lookup"><span data-stu-id="ad949-121">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="ad949-122">Они используются в условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="ad949-122">They are used to help in conditional compilation.</span></span> <span data-ttu-id="ad949-123">В отличие от директив C и C++ вы не можете использовать их для создания макросов.</span><span class="sxs-lookup"><span data-stu-id="ad949-123">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="ad949-124">Директива препроцессора должна быть единственной инструкцией в строке.</span><span class="sxs-lookup"><span data-stu-id="ad949-124">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad949-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ad949-125">See also</span></span>

- [<span data-ttu-id="ad949-126">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ad949-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ad949-127">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ad949-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
