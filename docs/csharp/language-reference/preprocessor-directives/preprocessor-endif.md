---
description: '#endif. Справочник по C#'
title: '#endif. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 0ccc00ceab2aa67c77140e3ef09907ba260d7e9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168638"
---
# <a name="endif-c-reference"></a><span data-ttu-id="aa04f-103">#endif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="aa04f-103">#endif (C# Reference)</span></span>

<span data-ttu-id="aa04f-104">`#endif` указывает на конец условной директивы, начало которой было задано с помощью директивы [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="aa04f-104">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="aa04f-105">Например,</span><span class="sxs-lookup"><span data-stu-id="aa04f-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="aa04f-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="aa04f-106">Remarks</span></span>  

 <span data-ttu-id="aa04f-107">Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="aa04f-107">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="aa04f-108">В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="aa04f-108">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa04f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="aa04f-109">See also</span></span>

- [<span data-ttu-id="aa04f-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="aa04f-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="aa04f-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="aa04f-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="aa04f-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="aa04f-112">C# Preprocessor Directives</span></span>](./index.md)
