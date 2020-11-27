---
title: illegalPrepareConstrainedRegion MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Иллегалпрепареконстраинедрегион, который вызывается, если за вызовом PrepareConstrainedRegions не следует инструкция Try.
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
ms.openlocfilehash: 7cbf04e8605ccf18e89882dd09b96cc7c59330c9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272791"
---
# <a name="illegalprepareconstrainedregion-mda"></a>illegalPrepareConstrainedRegion MDA

Помощник по отладке управляемого кода (MDA) `illegalPrepareConstrainedRegion` запускается, если сразу же после вызова метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> не следует инструкция `try` обработчика исключений. Это ограничение используется на уровне MSIL, поэтому между вызовом и `try` можно размещать текст, не приводящий к созданию кода, например комментарии.  
  
## <a name="symptoms"></a>Симптомы  

 Область ограниченного выполнения, которая никогда не рассматривается в виде такой области, но представляет собой простой блок обработки исключений (`finally` или `catch`). Поэтому эта область не запускается в случае нехватки памяти или прерывания потока.  
  
## <a name="cause"></a>Причина:  

 Вы не следуете шаблону подготовки для области ограниченного выполнения.  Это ошибка. <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>Вызов метода, используемый для пометки обработчиков исключений как знакомого CER в `catch` / `finally` / `fault` / `filter` блоках, должен использоваться непосредственно перед `try` инструкцией.  
  
## <a name="resolution"></a>Разрешение  

 Убедитесь, что вызов метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> выполняется непосредственно перед инструкцией `try`.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  

 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Выходные данные  

 Помощник по отладке управляемого кода отображает имя метода, вызывающего метод <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, смещение MSIL и сообщение о том, что вызов метода выполняется не перед началом блока try.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Пример  

 В следующем примере кода показан шаблон, который запускает этот помощник по отладке управляемого кода.  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [Диагностика ошибок посредством управляемых помощников по отладке](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
