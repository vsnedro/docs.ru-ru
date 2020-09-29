---
description: '#else. Справочник по C#'
title: '#else. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: f0dc8c34672c3e9e5a2207211794fbc8099640c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168677"
---
# <a name="else-c-reference"></a><span data-ttu-id="f274b-103">#else (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f274b-103">#else (C# Reference)</span></span>

<span data-ttu-id="f274b-104">С помощью директивы `#else` можно создать составную условную директиву со следующим поведением: если ни одно из выражений в предшествующих директивах [#if](./preprocessor-if.md) или (необязательно) [#elif](./preprocessor-elif.md) не принимает значение `true`, компилятор выполняет код между директивой `#else` и последующей директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="f274b-104">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f274b-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="f274b-105">Remarks</span></span>  

 <span data-ttu-id="f274b-106">Директива [#endif](./preprocessor-endif.md) обязательно указывается в качестве следующей директивы препроцессора после `#else`.</span><span class="sxs-lookup"><span data-stu-id="f274b-106">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="f274b-107">В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#else`.</span><span class="sxs-lookup"><span data-stu-id="f274b-107">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f274b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="f274b-108">See also</span></span>

- [<span data-ttu-id="f274b-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f274b-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f274b-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f274b-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f274b-111">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="f274b-111">C# Preprocessor Directives</span></span>](./index.md)
