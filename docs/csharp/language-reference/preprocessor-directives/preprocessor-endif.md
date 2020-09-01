---
description: '#endif. Справочник по C#'
title: '#endif. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 8068a6e437145178fd5c88763c86692a8700c349
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138167"
---
# <a name="endif-c-reference"></a><span data-ttu-id="576d1-103">#endif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="576d1-103">#endif (C# Reference)</span></span>
<span data-ttu-id="576d1-104">`#endif` указывает на конец условной директивы, начало которой было задано с помощью директивы [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="576d1-104">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="576d1-105">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="576d1-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="576d1-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="576d1-106">Remarks</span></span>  
 <span data-ttu-id="576d1-107">Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="576d1-107">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="576d1-108">В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="576d1-108">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="576d1-109">См. также</span><span class="sxs-lookup"><span data-stu-id="576d1-109">See also</span></span>

- [<span data-ttu-id="576d1-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="576d1-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="576d1-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="576d1-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="576d1-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="576d1-112">C# Preprocessor Directives</span></span>](./index.md)
