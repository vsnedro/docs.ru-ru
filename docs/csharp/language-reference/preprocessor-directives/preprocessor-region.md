---
title: '#region. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: 66583d6e067b006b03130d8ff842b56bf57bcebc
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802778"
---
# <a name="region-c-reference"></a><span data-ttu-id="f3d38-102">#region (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f3d38-102">#region (C# Reference)</span></span>
<span data-ttu-id="f3d38-103">Директива `#region` позволяет указать блок кода, который можно разворачивать и сворачивать с помощью функции [структурирования](/visualstudio/ide/outlining) в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="f3d38-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the code editor.</span></span> <span data-ttu-id="f3d38-104">В больших файлах кода удобно сворачивать или скрывать одну или несколько областей, чтобы не отвлекаться от той части файла, над которой в настоящее время идет работа.</span><span class="sxs-lookup"><span data-stu-id="f3d38-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="f3d38-105">В следующем примере показано, как определить область:</span><span class="sxs-lookup"><span data-stu-id="f3d38-105">The following example shows how to define a region:</span></span>  
  
```csharp
#region MyClass definition  
public class MyClass
{  
    static void Main()
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a><span data-ttu-id="f3d38-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3d38-106">Remarks</span></span>  
 <span data-ttu-id="f3d38-107">В конце блока `#region` должна присутствовать директива [#endregion](./preprocessor-endregion.md).</span><span class="sxs-lookup"><span data-stu-id="f3d38-107">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="f3d38-108">Блок `#region` не может накладываться на блок [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="f3d38-108">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="f3d38-109">Однако блок `#region` можно вложить в блок `#if`, а блок `#if` — в блок `#region`.</span><span class="sxs-lookup"><span data-stu-id="f3d38-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d38-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f3d38-110">See also</span></span>

- [<span data-ttu-id="f3d38-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f3d38-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f3d38-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f3d38-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f3d38-113">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="f3d38-113">C# Preprocessor Directives</span></span>](./index.md)
