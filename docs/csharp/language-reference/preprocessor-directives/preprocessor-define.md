---
description: '#Справочник по C#. Директива #define'
title: '#Справочник по C#. Директива #define'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: 961c20c091a4a6d7da421d94500abd41d2d60a5b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160506"
---
# <a name="define-c-reference"></a><span data-ttu-id="01125-103">#define (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="01125-103">#define (C# Reference)</span></span>

<span data-ttu-id="01125-104">`#define` позволяет определить символ.</span><span class="sxs-lookup"><span data-stu-id="01125-104">You use `#define` to define a symbol.</span></span> <span data-ttu-id="01125-105">При использовании символа в качестве выражения, которое передается директиве [#if](./preprocessor-if.md), выражение будет иметь значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="01125-105">When you use the symbol as the expression that's passed to the [#if](./preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  

 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="01125-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="01125-106">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01125-107">Директиву `#define` нельзя использовать для объявления значений констант, как это обычно делается в C и C++.</span><span class="sxs-lookup"><span data-stu-id="01125-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="01125-108">Для определения констант в C# следует использовать статические элементы класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="01125-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="01125-109">При наличии нескольких констант имеет смысл создать для них отдельный класс "Constants".</span><span class="sxs-lookup"><span data-stu-id="01125-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="01125-110">Символы можно использовать для указания условий компиляции.</span><span class="sxs-lookup"><span data-stu-id="01125-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="01125-111">Для проверки символов можно использовать директивы [#if](./preprocessor-if.md) или [#elif](./preprocessor-elif.md).</span><span class="sxs-lookup"><span data-stu-id="01125-111">You can test for the symbol with either [#if](./preprocessor-if.md) or [#elif](./preprocessor-elif.md).</span></span> <span data-ttu-id="01125-112">Для условной компиляции также можно использовать <xref:System.Diagnostics.ConditionalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="01125-112">You can also use the <xref:System.Diagnostics.ConditionalAttribute> to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="01125-113">Можно определить символ, но нельзя назначить символу значение.</span><span class="sxs-lookup"><span data-stu-id="01125-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="01125-114">Директива `#define` должна находиться в файле перед использованием любых инструкций, которые также не являются директивами препроцессора.</span><span class="sxs-lookup"><span data-stu-id="01125-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="01125-115">Также символ можно определить с помощью параметра компилятора [-define](../compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="01125-115">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="01125-116">Для отмены определения символа служит директива [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="01125-116">You can undefine a symbol with [#undef](./preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="01125-117">Символ, определенный с помощью `-define` или `#define`, не конфликтует с одноименной переменной.</span><span class="sxs-lookup"><span data-stu-id="01125-117">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="01125-118">Соответственно, имя переменной не должно передаваться директиве препроцессора, а символ может использоваться только в директиве препроцессора.</span><span class="sxs-lookup"><span data-stu-id="01125-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="01125-119">Область символа, которая была создана с помощью директивы `#define`, — это файл, в котором был определен символ.</span><span class="sxs-lookup"><span data-stu-id="01125-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="01125-120">Как показано в следующем примере, необходимо поместить директивы `#define` в верхнюю часть файла.</span><span class="sxs-lookup"><span data-stu-id="01125-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 <span data-ttu-id="01125-121">Пример отмены определения символа см. в разделе [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="01125-121">For an example of how to undefine a symbol, see [#undef](./preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01125-122">См. также</span><span class="sxs-lookup"><span data-stu-id="01125-122">See also</span></span>

- [<span data-ttu-id="01125-123">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="01125-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="01125-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="01125-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="01125-125">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="01125-125">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="01125-126">const</span><span class="sxs-lookup"><span data-stu-id="01125-126">const</span></span>](../keywords/const.md)
- <span data-ttu-id="01125-127">[Практическое руководство. Условная компиляция с использованием атрибутов Trace и Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).</span><span class="sxs-lookup"><span data-stu-id="01125-127">[How to: Compile Conditionally with Trace and Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)</span></span>
- [<span data-ttu-id="01125-128">#undef</span><span class="sxs-lookup"><span data-stu-id="01125-128">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="01125-129">#if</span><span class="sxs-lookup"><span data-stu-id="01125-129">#if</span></span>](./preprocessor-if.md)
