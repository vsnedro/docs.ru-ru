---
title: Переадресация типов в общеязыковой среде CLR
description: Перенаправление типа позволяет переместить тип в другую сборку .NET без повторной компиляции приложений, использующих исходную сборку.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: f0be61bd4ce88569e22a350a9ea9490d67e74ff3
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378596"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="9fc26-103">Переадресация типов в общеязыковой среде CLR</span><span class="sxs-lookup"><span data-stu-id="9fc26-103">Type forwarding in the common language runtime</span></span>
<span data-ttu-id="9fc26-104">Перенаправление типа позволяет переместить тип в другую сборку без повторной компиляции приложений, использующих исходную сборку.</span><span class="sxs-lookup"><span data-stu-id="9fc26-104">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="9fc26-105">Предположим, например, что приложение использует класс `Example` в сборке с именем *Utility.dll*.</span><span class="sxs-lookup"><span data-stu-id="9fc26-105">For example, suppose an application uses the `Example` class in an assembly named *Utility.dll*.</span></span> <span data-ttu-id="9fc26-106">Разработчики *Utility.dll* могут принять решение выполнить рефакторинг сборки и в ходе этого процесса могут переместить класс `Example` в другую сборку.</span><span class="sxs-lookup"><span data-stu-id="9fc26-106">The developers of *Utility.dll* might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="9fc26-107">Если старую версию *Utility.dll* заменить новой версией *Utility.dll* и ее сопутствующей сборкой, приложение, использующее класс `Example`, завершится ошибкой, так как не сможет найти класс `Example` в новой версии *Utility.dll*.</span><span class="sxs-lookup"><span data-stu-id="9fc26-107">If the old version of *Utility.dll* is replaced by the new version of *Utility.dll* and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of *Utility.dll*.</span></span>  
  
 <span data-ttu-id="9fc26-108">Разработчики *Utility.dll* могут избежать этого, перенаправляя запросы к классу `Example` с помощью атрибута <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9fc26-108">The developers of *Utility.dll* can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="9fc26-109">Если атрибут применен к новой версии *Utility.dll*, запросы класса `Example` перенаправляются в сборку, которая теперь содержит этот класс.</span><span class="sxs-lookup"><span data-stu-id="9fc26-109">If the attribute has been applied to the new version of *Utility.dll*, requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="9fc26-110">Существующее приложение продолжает нормально функционировать без перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="9fc26-110">The existing application continues to function normally, without recompilation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fc26-111">В платформе .NET Framework версии 2.0 нельзя перенаправлять типы из сборок, написанных на Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9fc26-111">In the .NET Framework version 2.0, you cannot forward types from assemblies written in Visual Basic.</span></span> <span data-ttu-id="9fc26-112">Тем не менее приложения, написанные на Visual Basic, могут использовать перенаправленные типы.</span><span class="sxs-lookup"><span data-stu-id="9fc26-112">However, an application written in Visual Basic can consume forwarded types.</span></span> <span data-ttu-id="9fc26-113">То есть если приложение использует сборку, написанную на языке C# или C++, и тип из этой сборки перенаправляется в другую сборку, приложение Visual Basic можно использовать перенаправленный тип.</span><span class="sxs-lookup"><span data-stu-id="9fc26-113">That is, if the application uses an assembly coded in C# or C++, and a type from that assembly is forwarded to another assembly, the Visual Basic application can use the forwarded type.</span></span>  
  
## <a name="forward-types"></a><span data-ttu-id="9fc26-114">Переадресация типов</span><span class="sxs-lookup"><span data-stu-id="9fc26-114">Forward types</span></span>  
 <span data-ttu-id="9fc26-115">Для перенаправления типа следует выполнить следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="9fc26-115">There are four steps to forwarding a type:</span></span>  
  
1. <span data-ttu-id="9fc26-116">Переместите исходный код для типа из исходной сборки в целевую сборку.</span><span class="sxs-lookup"><span data-stu-id="9fc26-116">Move the source code for the type from the original assembly to the destination assembly.</span></span>  

2. <span data-ttu-id="9fc26-117">В сборке, где раньше находился тип, добавьте <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> для типа, который был перемещен.</span><span class="sxs-lookup"><span data-stu-id="9fc26-117">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="9fc26-118">В следующем коде показан атрибут для типа с именем `Example`, который был перемещен.</span><span class="sxs-lookup"><span data-stu-id="9fc26-118">The following code shows the attribute for a type named `Example` that was moved.</span></span>  

   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```

   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  

3. <span data-ttu-id="9fc26-119">Скомпилируйте сборку, которая теперь содержит тип.</span><span class="sxs-lookup"><span data-stu-id="9fc26-119">Compile the assembly that now contains the type.</span></span>  

4. <span data-ttu-id="9fc26-120">Перекомпилируйте сборку, где раньше находился тип, со ссылкой на сборку, которая теперь содержит тип.</span><span class="sxs-lookup"><span data-stu-id="9fc26-120">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="9fc26-121">Например, при компиляции файла C# из командной строки используйте параметр [-reference (параметры компилятора C#)](../../csharp/language-reference/compiler-options/reference-compiler-option.md), чтобы указать сборку, содержащую тип.</span><span class="sxs-lookup"><span data-stu-id="9fc26-121">For example, if you are compiling a C# file from the command line, use the [-reference (C# compiler options)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="9fc26-122">В C++ используйте директиву [#using](/cpp/preprocessor/hash-using-directive-cpp) в исходном файле, чтобы указать сборку, содержащую тип.</span><span class="sxs-lookup"><span data-stu-id="9fc26-122">In C++, use the [#using](/cpp/preprocessor/hash-using-directive-cpp) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fc26-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9fc26-123">See also</span></span>

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [<span data-ttu-id="9fc26-124">Перенаправление типов (C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="9fc26-124">Type forwarding (C++/CLI)</span></span>](/cpp/windows/type-forwarding-cpp-cli)
- [<span data-ttu-id="9fc26-125">Директива #using</span><span class="sxs-lookup"><span data-stu-id="9fc26-125">#using directive</span></span>](/cpp/preprocessor/hash-using-directive-cpp)
