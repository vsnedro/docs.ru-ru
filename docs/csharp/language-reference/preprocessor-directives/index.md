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
ms.openlocfilehash: a7ffca8b39f1bd9f05193bccbb6d90e67fa262c9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132369"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="407c2-103">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="407c2-103">C# preprocessor directives</span></span>
<span data-ttu-id="407c2-104">В этом разделе содержатся сведения о следующих директивах препроцессора C#:</span><span class="sxs-lookup"><span data-stu-id="407c2-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="407c2-105">#if</span><span class="sxs-lookup"><span data-stu-id="407c2-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="407c2-106">#else</span><span class="sxs-lookup"><span data-stu-id="407c2-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="407c2-107">#elif</span><span class="sxs-lookup"><span data-stu-id="407c2-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="407c2-108">#endif</span><span class="sxs-lookup"><span data-stu-id="407c2-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="407c2-109">#define</span><span class="sxs-lookup"><span data-stu-id="407c2-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="407c2-110">#undef</span><span class="sxs-lookup"><span data-stu-id="407c2-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="407c2-111">#warning</span><span class="sxs-lookup"><span data-stu-id="407c2-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="407c2-112">#error</span><span class="sxs-lookup"><span data-stu-id="407c2-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="407c2-113">#line</span><span class="sxs-lookup"><span data-stu-id="407c2-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="407c2-114">#region</span><span class="sxs-lookup"><span data-stu-id="407c2-114">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="407c2-115">#endregion</span><span class="sxs-lookup"><span data-stu-id="407c2-115">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="407c2-116">#pragma</span><span class="sxs-lookup"><span data-stu-id="407c2-116">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="407c2-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="407c2-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="407c2-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="407c2-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="407c2-119">Дополнительные сведения и примеры см. в разделах по каждой из этих директив.</span><span class="sxs-lookup"><span data-stu-id="407c2-119">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="407c2-120">Хотя у компилятора нет отдельного препроцессора, директивы, описанные в этом разделе, обрабатываются так, как если бы он был.</span><span class="sxs-lookup"><span data-stu-id="407c2-120">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="407c2-121">Они используются в условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="407c2-121">They are used to help in conditional compilation.</span></span> <span data-ttu-id="407c2-122">В отличие от директив C и C++ вы не можете использовать их для создания макросов.</span><span class="sxs-lookup"><span data-stu-id="407c2-122">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="407c2-123">Директива препроцессора должна быть единственной инструкцией в строке.</span><span class="sxs-lookup"><span data-stu-id="407c2-123">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="407c2-124">См. также</span><span class="sxs-lookup"><span data-stu-id="407c2-124">See also</span></span>

- [<span data-ttu-id="407c2-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="407c2-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="407c2-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="407c2-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
