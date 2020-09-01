---
description: '#warning. Справочник по C#'
title: '#warning. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: ab2cc5120492fc2a4b94296eb85e563c0a1d5ad3
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137842"
---
# <a name="warning-c-reference"></a><span data-ttu-id="50190-103">#warning (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="50190-103">#warning (C# Reference)</span></span>
<span data-ttu-id="50190-104">`#warning` позволяет создать предупреждение компилятора [CS1030](../../misc/cs1030.md) первого уровня из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="50190-104">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="50190-105">Пример:</span><span class="sxs-lookup"><span data-stu-id="50190-105">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="50190-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="50190-106">Remarks</span></span>
 <span data-ttu-id="50190-107">Как правило, `#warning` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="50190-107">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="50190-108">Кроме того, с помощью директивы [#error](./preprocessor-error.md) можно создать определяемую пользователем ошибку.</span><span class="sxs-lookup"><span data-stu-id="50190-108">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="50190-109">Пример</span><span class="sxs-lookup"><span data-stu-id="50190-109">Example</span></span>  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="50190-110">См. также</span><span class="sxs-lookup"><span data-stu-id="50190-110">See also</span></span>

- [<span data-ttu-id="50190-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="50190-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="50190-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="50190-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="50190-113">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="50190-113">C# Preprocessor Directives</span></span>](./index.md)
