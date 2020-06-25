---
title: Помощник по отладке управляемого кода jitCompilationStart (MDA)
description: Помощник по отладке управляемого кода jitCompilationStart (MDA) сообщает, когда JIT-компилятор начинает компиляцию функции .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
ms.openlocfilehash: 13e20c1a940b7bfa777245ba35f3cc1b003d15b2
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325529"
---
# <a name="jitcompilationstart-mda"></a>jitCompilationStart MDA

Помощник по отладке управляемого кода (MDA) `jitCompilationStart` активируется, чтобы сообщить о том, что JIT-компилятор начал компиляцию функции.  
  
## <a name="symptoms"></a>Симптомы  
 Размер рабочего набора увеличивается для программы, которая уже находится в формате собственного образа, поскольку mscorjit.dll загружается в процесс.  
  
## <a name="cause"></a>Причина  
Не все сборки, от которых зависит программа, были созданы в собственном формате или сборка не зарегистрирована должным образом.  

## <a name="resolution"></a>Решение  
 Включение этого MDA позволяет выяснить, какая функция JIT-скомпилирована. Убедитесь, что сборка, содержащая функцию, создана в собственном формате и правильно зарегистрирована.
  
## <a name="effect-on-the-runtime"></a>Воздействие на среду выполнения  
 Этот помощник по отладке управляемого кода записывает сообщение непосредственно перед компиляцией метода с помощью JIT-компилятора, поэтому включение этого помощника оказывает значительное влияние на производительность. Если метод является встроенным, этот MDA не будет создавать отдельное сообщение.  
  
## <a name="output"></a>Выходные данные  
 Ниже приведен пример выходных данных. В этом случае выходные данные показывают, что в тесте сборки метод "m" для класса "ns2.CO" был скомпилирован JIT-компилятором.  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a>Параметр Configuration  
 Приведенный ниже файл конфигурации содержит различные фильтры, которые можно применять, чтобы отфильтровать методы, о которых будет сообщено при их первой JIT-компиляции. Можно указать, чтобы все методы были переданы, задав для атрибута Name значение \* .  
  
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
  
## <a name="example"></a>Пример  
 Приведенный ниже пример кода предназначен для использования с предыдущим файлом конфигурации.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством управляемых помощников по отладке](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
