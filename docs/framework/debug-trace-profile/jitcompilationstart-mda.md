---
title: jitCompilationStart MDA
description: Используйте помощник по отладке управляемого кода jitCompilationStart (MDA), который запускается для отчета, когда JIT-компилятор начинает компиляцию функции .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
ms.openlocfilehash: bf2d09f433f0b8e4056fecd1f4e82bf3b91dd2bc
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904134"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="20130-103">jitCompilationStart MDA</span><span class="sxs-lookup"><span data-stu-id="20130-103">jitCompilationStart MDA</span></span>
<span data-ttu-id="20130-104">Помощник по отладке управляемого кода (MDA) `jitCompilationStart` активируется, чтобы сообщить о том, что JIT-компилятор начал компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="20130-104">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="20130-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="20130-105">Symptoms</span></span>  
 <span data-ttu-id="20130-106">Размер рабочего набора для программы, уже находящейся в формате образа в машинном коде, увеличивается, так как в процесс загружается библиотека mscorjit.dll.</span><span class="sxs-lookup"><span data-stu-id="20130-106">The working set size increases for a program that is already in native image format because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="20130-107">Причина</span><span class="sxs-lookup"><span data-stu-id="20130-107">Cause</span></span>  
 <span data-ttu-id="20130-108">Не все сборки, от которых зависит программа, были сгенерированы в собственном формате, либо те сборки, которые были сгенерированы в этом формате, не были правильно зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="20130-108">Not all the assemblies the program depends on have been generated into native format, or those that have are not registered correctly.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="20130-109">Решение</span><span class="sxs-lookup"><span data-stu-id="20130-109">Resolution</span></span>  
 <span data-ttu-id="20130-110">Включение этого помощника по отладке управляемого кода позволяет определить, какие функции были скомпилированы посредством JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="20130-110">Enabling this MDA allows you to determine which function is being JIT-compiled.</span></span> <span data-ttu-id="20130-111">Следует определить, была ли сборка, содержащая функцию, сгенерирована в собственном формате и правильно зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="20130-111">Determine whether the assembly that contains the function is generated to native format and properly registered.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="20130-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="20130-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="20130-113">Этот помощник по отладке управляемого кода записывает сообщение непосредственно перед компиляцией метода с помощью JIT-компилятора, поэтому включение этого помощника оказывает значительное влияние на производительность.</span><span class="sxs-lookup"><span data-stu-id="20130-113">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="20130-114">Обратите внимание, что если метод является встроенным, этот помощник по отладке управляемого кода не будет создавать отдельное сообщение.</span><span class="sxs-lookup"><span data-stu-id="20130-114">Note that if a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="20130-115">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="20130-115">Output</span></span>  
 <span data-ttu-id="20130-116">Ниже приведен пример выходных данных.</span><span class="sxs-lookup"><span data-stu-id="20130-116">The following code sample shows sample output.</span></span> <span data-ttu-id="20130-117">В этом случае видно, что в сборке Test метод m класса ns2.CO был скомпилирован посредством JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="20130-117">In this case the output shows that in assembly Test the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="20130-118">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="20130-118">Configuration</span></span>  
 <span data-ttu-id="20130-119">Приведенный ниже файл конфигурации содержит различные фильтры, которые можно применять, чтобы отфильтровать методы, о которых будет сообщено при их первой JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="20130-119">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="20130-120">Можно указать, чтобы все методы были переданы, задав для атрибута Name значение \* .</span><span class="sxs-lookup"><span data-stu-id="20130-120">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="20130-121">Пример</span><span class="sxs-lookup"><span data-stu-id="20130-121">Example</span></span>  
 <span data-ttu-id="20130-122">Приведенный ниже пример кода предназначен для использования с предыдущим файлом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="20130-122">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```csharp
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="20130-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="20130-123">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="20130-124">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="20130-124">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="20130-125">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="20130-125">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
