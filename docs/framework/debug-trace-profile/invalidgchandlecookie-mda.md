---
title: invalidGCHandleCookie MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Инвалидгчандлекукие (MDA), который активируется при попытке преобразования из недопустимого файла cookie IntPtr в GCHandle.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
ms.openlocfilehash: 1063b7be902d3063717b6639564d819ef3292c0e
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051302"
---
# <a name="invalidgchandlecookie-mda"></a><span data-ttu-id="11617-103">invalidGCHandleCookie MDA</span><span class="sxs-lookup"><span data-stu-id="11617-103">invalidGCHandleCookie MDA</span></span>
<span data-ttu-id="11617-104">Помощник по отладке управляемого кода (MDA) `invalidGCHandleCookie` активируется при попытке преобразования из недопустимого файла cookie <xref:System.IntPtr> в <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="11617-104">The `invalidGCHandleCookie` managed debugging assistant (MDA) is activated when a conversion from an invalid <xref:System.IntPtr> cookie to a <xref:System.Runtime.InteropServices.GCHandle> is attempted.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="11617-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="11617-105">Symptoms</span></span>  
 <span data-ttu-id="11617-106">Неопределенное поведение, например нарушения прав доступа и повреждение памяти, при попытке использовать или получить <xref:System.Runtime.InteropServices.GCHandle> из <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="11617-106">Undefined behavior such as access violations and memory corruption while attempting to use or retrieve a <xref:System.Runtime.InteropServices.GCHandle> from an <xref:System.IntPtr>.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="11617-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="11617-107">Cause</span></span>  
 <span data-ttu-id="11617-108">Возможно, файл cookie является недопустимым, так как он не был изначально создан из <xref:System.Runtime.InteropServices.GCHandle>, представляет <xref:System.Runtime.InteropServices.GCHandle>, который уже был освобожден, является файлом cookie для <xref:System.Runtime.InteropServices.GCHandle> в другом домене приложения или был упакован в собственный код как <xref:System.Runtime.InteropServices.GCHandle>, но передан обратно в среду CLR в качестве <xref:System.IntPtr>, где была выполнена попытка приведения к типу.</span><span class="sxs-lookup"><span data-stu-id="11617-108">The cookie is probably invalid because it was not originally created from a <xref:System.Runtime.InteropServices.GCHandle>, represents a <xref:System.Runtime.InteropServices.GCHandle> that has already been freed, is a cookie to a <xref:System.Runtime.InteropServices.GCHandle> in a different application domain, or was marshaled to native code as a <xref:System.Runtime.InteropServices.GCHandle> but passed back into the CLR as an <xref:System.IntPtr>, where a cast was attempted.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="11617-109">Решение</span><span class="sxs-lookup"><span data-stu-id="11617-109">Resolution</span></span>  
 <span data-ttu-id="11617-110">Укажите допустимый файл cookie <xref:System.IntPtr> для <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="11617-110">Specify a valid <xref:System.IntPtr> cookie for the <xref:System.Runtime.InteropServices.GCHandle>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="11617-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="11617-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="11617-112">Если этот MDA включен, отладчик больше не может отслеживать корни обратно в их объекты, поскольку значения файла cookie, переданные обратно, отличаются от значений, возвращаемых при отключенном MDA.</span><span class="sxs-lookup"><span data-stu-id="11617-112">When this MDA is enabled, the debugger is no longer able to trace the roots back to their objects because the cookie values passed back are different from the ones returned when the MDA is not enabled.</span></span>  
  
## <a name="output"></a><span data-ttu-id="11617-113">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="11617-113">Output</span></span>  
 <span data-ttu-id="11617-114">Указывается значение недопустимого файла cookie <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="11617-114">The invalid <xref:System.IntPtr> cookie value is reported.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="11617-115">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="11617-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="11617-116">См. также</span><span class="sxs-lookup"><span data-stu-id="11617-116">See also</span></span>

- <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>
- <xref:System.Runtime.InteropServices.GCHandle>
- [<span data-ttu-id="11617-117">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="11617-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
