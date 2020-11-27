---
title: Помощник по отладке управляемого кода reportAvOnComRelease
description: Ознакомьтесь с помощником по отладке управляемого кода Репортавонкомрелеасе (MDA), который может быть активирован из-за нарушений прав доступа и повреждения памяти в .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
ms.openlocfilehash: c5047aa4005cdaa9ae6aabe8dcd7ee838ee13f58
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267121"
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="357cd-103">Помощник по отладке управляемого кода reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="357cd-103">reportAvOnComRelease MDA</span></span>

<span data-ttu-id="357cd-104">Помощник отладки управляемого кода (MDA) `reportAvOnComRelease` активируется при возникновении исключений, вызванных ошибками подсчета пользовательских ссылок при выполнении COM-взаимодействия и использовании метода <xref:System.Runtime.InteropServices.Marshal.Release%2A> или <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> в сочетании с необработанными вызовами COM.</span><span class="sxs-lookup"><span data-stu-id="357cd-104">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="357cd-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="357cd-105">Symptoms</span></span>  

 <span data-ttu-id="357cd-106">Нарушения прав доступа и повреждение памяти.</span><span class="sxs-lookup"><span data-stu-id="357cd-106">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="357cd-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="357cd-107">Cause</span></span>  

 <span data-ttu-id="357cd-108">Иногда исключение возникает в связи с ошибками подсчета пользовательских ссылок при выполнении COM-взаимодействия и использовании метода <xref:System.Runtime.InteropServices.Marshal.Release%2A> или <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> в сочетании с необработанными вызовами COM.</span><span class="sxs-lookup"><span data-stu-id="357cd-108">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="357cd-109">Обычно это исключение отменяется, так как в противном случае в среде CLR произойдет нарушение прав доступа, и работа среды будет завершена.</span><span class="sxs-lookup"><span data-stu-id="357cd-109">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="357cd-110">Когда этот помощник включен, такие исключения вместо простой отмены можно обнаруживать и выводить в отчетах.</span><span class="sxs-lookup"><span data-stu-id="357cd-110">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="357cd-111">Разрешение</span><span class="sxs-lookup"><span data-stu-id="357cd-111">Resolution</span></span>  

 <span data-ttu-id="357cd-112">Изучите свой код подсчета ссылок для поиска ошибок и проверки собственных клиентов объекта на наличие ошибок подсчета ссылок.</span><span class="sxs-lookup"><span data-stu-id="357cd-112">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="357cd-113">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="357cd-113">Effect on the Runtime</span></span>  

 <span data-ttu-id="357cd-114">Доступно два режима.</span><span class="sxs-lookup"><span data-stu-id="357cd-114">Two modes are available.</span></span> <span data-ttu-id="357cd-115">Если атрибут `allowAv` имеет значение `true`, помощник запрещает среде выполнения отменить нарушение прав доступа.</span><span class="sxs-lookup"><span data-stu-id="357cd-115">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="357cd-116">Если `allowAv` имеет значение `false`, которое используется по умолчанию, среды выполнения отменяет нарушение прав доступа, однако пользователь получает предупреждение о возникновении и отмене исключения.</span><span class="sxs-lookup"><span data-stu-id="357cd-116">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="357cd-117">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="357cd-117">Output</span></span>  

 <span data-ttu-id="357cd-118">Когда это возможно, выходные данные содержат исходный vtable указателя интерфейса COM.</span><span class="sxs-lookup"><span data-stu-id="357cd-118">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="357cd-119">В противном случае отображается информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="357cd-119">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="357cd-120">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="357cd-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="357cd-121">См. также</span><span class="sxs-lookup"><span data-stu-id="357cd-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="357cd-122">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="357cd-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="357cd-123">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="357cd-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
