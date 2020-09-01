---
description: '#Справочник по C#. #pragma warning'
title: '#Справочник по C#. #pragma warning'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 3085c21db386ca215d48bbe8ade83cd26732242c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137972"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="70ccf-103">#pragma warning (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="70ccf-103">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="70ccf-104">`#pragma warning` может включать или отключать определенные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="70ccf-104">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70ccf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70ccf-105">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="70ccf-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="70ccf-106">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="70ccf-107">Список номеров предупреждений с разделителем-запятой.</span><span class="sxs-lookup"><span data-stu-id="70ccf-107">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="70ccf-108">Префикс CS является необязательным.</span><span class="sxs-lookup"><span data-stu-id="70ccf-108">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="70ccf-109">Если номера предупреждений не указаны, `disable` отключает все предупреждения, а `restore` включает все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="70ccf-109">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70ccf-110">Чтобы найти номера предупреждений в Visual Studio, выполните сборку проекта, а затем поиск номеров предупреждений в окне **Вывод**.</span><span class="sxs-lookup"><span data-stu-id="70ccf-110">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70ccf-111">Пример</span><span class="sxs-lookup"><span data-stu-id="70ccf-111">Example</span></span>  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="70ccf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="70ccf-112">See also</span></span>

- [<span data-ttu-id="70ccf-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="70ccf-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="70ccf-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="70ccf-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="70ccf-115">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="70ccf-115">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="70ccf-116">Ошибки компилятора C#</span><span class="sxs-lookup"><span data-stu-id="70ccf-116">C# Compiler Errors</span></span>](../compiler-messages/index.md)
