---
description: '#else. Справочник по C#'
title: '#else. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: fb1a9f30a42c78b5c4c7323ec213ab8c20b9bb76
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138180"
---
# <a name="else-c-reference"></a><span data-ttu-id="cf4ba-103">#else (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="cf4ba-103">#else (C# Reference)</span></span>
<span data-ttu-id="cf4ba-104">С помощью директивы `#else` можно создать составную условную директиву со следующим поведением: если ни одно из выражений в предшествующих директивах [#if](./preprocessor-if.md) или (необязательно) [#elif](./preprocessor-elif.md) не принимает значение `true`, компилятор выполняет код между директивой `#else` и последующей директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="cf4ba-104">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf4ba-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf4ba-105">Remarks</span></span>  
 <span data-ttu-id="cf4ba-106">Директива [#endif](./preprocessor-endif.md) обязательно указывается в качестве следующей директивы препроцессора после `#else`.</span><span class="sxs-lookup"><span data-stu-id="cf4ba-106">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="cf4ba-107">В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#else`.</span><span class="sxs-lookup"><span data-stu-id="cf4ba-107">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf4ba-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cf4ba-108">See also</span></span>

- [<span data-ttu-id="cf4ba-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="cf4ba-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cf4ba-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cf4ba-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cf4ba-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="cf4ba-111">C# Preprocessor Directives</span></span>](./index.md)
