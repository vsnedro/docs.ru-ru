---
description: '#elif. Справочник по C#'
title: '#elif. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 383c143792a39bb3abcd255804360ad5e2f8ef74
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168703"
---
# <a name="elif-c-reference"></a><span data-ttu-id="8d151-103">#elif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8d151-103">#elif (C# Reference)</span></span>

<span data-ttu-id="8d151-104">Директива `#elif` позволяет создать составную условную директиву.</span><span class="sxs-lookup"><span data-stu-id="8d151-104">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="8d151-105">Выражение `#elif` будет вычисляться в том случае, если ни одна из предшествующих директив [#if](./preprocessor-if.md) или необязательных директив `#elif` после вычисления выражения не возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="8d151-105">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="8d151-106">Если после вычисления выражения `#elif` возвращается значение `true`, компилятор вычисляет весь код между директивой `#elif` и следующей условной директивой.</span><span class="sxs-lookup"><span data-stu-id="8d151-106">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="8d151-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="8d151-107">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="8d151-108">Для вычисления нескольких символов можно использовать операторы `==` (равенство), `!=` (неравенство), `&&` (И) и `||` (ИЛИ).</span><span class="sxs-lookup"><span data-stu-id="8d151-108">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="8d151-109">Можно также группировать символы и операторы при помощи скобок.</span><span class="sxs-lookup"><span data-stu-id="8d151-109">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d151-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8d151-110">Remarks</span></span>  

 <span data-ttu-id="8d151-111">Применение `#elif` эквивалентно следующему:</span><span class="sxs-lookup"><span data-stu-id="8d151-111">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="8d151-112">Директива `#elif` позволяет упростить код, поскольку для каждой директивы `#if` требуется отдельная директива [#endif](./preprocessor-endif.md), тогда как `#elif` можно использовать без соответствующей директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="8d151-112">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="8d151-113">В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#elif`.</span><span class="sxs-lookup"><span data-stu-id="8d151-113">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d151-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8d151-114">See also</span></span>

- [<span data-ttu-id="8d151-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8d151-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8d151-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8d151-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8d151-117">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="8d151-117">C# Preprocessor Directives</span></span>](./index.md)
