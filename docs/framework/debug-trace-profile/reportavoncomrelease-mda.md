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
ms.openlocfilehash: f9ba343060cb4d16de5909a5b619353546aca8ca
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803614"
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="77252-103">Помощник по отладке управляемого кода reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="77252-103">reportAvOnComRelease MDA</span></span>
<span data-ttu-id="77252-104">Помощник отладки управляемого кода (MDA) `reportAvOnComRelease` активируется при возникновении исключений, вызванных ошибками подсчета пользовательских ссылок при выполнении COM-взаимодействия и использовании метода <xref:System.Runtime.InteropServices.Marshal.Release%2A> или <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> в сочетании с необработанными вызовами COM.</span><span class="sxs-lookup"><span data-stu-id="77252-104">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="77252-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="77252-105">Symptoms</span></span>  
 <span data-ttu-id="77252-106">Нарушения прав доступа и повреждение памяти.</span><span class="sxs-lookup"><span data-stu-id="77252-106">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="77252-107">Причина</span><span class="sxs-lookup"><span data-stu-id="77252-107">Cause</span></span>  
 <span data-ttu-id="77252-108">Иногда исключение возникает в связи с ошибками подсчета пользовательских ссылок при выполнении COM-взаимодействия и использовании метода <xref:System.Runtime.InteropServices.Marshal.Release%2A> или <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> в сочетании с необработанными вызовами COM.</span><span class="sxs-lookup"><span data-stu-id="77252-108">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="77252-109">Обычно это исключение отменяется, так как в противном случае в среде CLR произойдет нарушение прав доступа, и работа среды будет завершена.</span><span class="sxs-lookup"><span data-stu-id="77252-109">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="77252-110">Когда этот помощник включен, такие исключения вместо простой отмены можно обнаруживать и выводить в отчетах.</span><span class="sxs-lookup"><span data-stu-id="77252-110">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="77252-111">Решение</span><span class="sxs-lookup"><span data-stu-id="77252-111">Resolution</span></span>  
 <span data-ttu-id="77252-112">Изучите свой код подсчета ссылок для поиска ошибок и проверки собственных клиентов объекта на наличие ошибок подсчета ссылок.</span><span class="sxs-lookup"><span data-stu-id="77252-112">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="77252-113">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="77252-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="77252-114">Доступно два режима.</span><span class="sxs-lookup"><span data-stu-id="77252-114">Two modes are available.</span></span> <span data-ttu-id="77252-115">Если атрибут `allowAv` имеет значение `true`, помощник запрещает среде выполнения отменить нарушение прав доступа.</span><span class="sxs-lookup"><span data-stu-id="77252-115">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="77252-116">Если `allowAv` имеет значение `false`, которое используется по умолчанию, среды выполнения отменяет нарушение прав доступа, однако пользователь получает предупреждение о возникновении и отмене исключения.</span><span class="sxs-lookup"><span data-stu-id="77252-116">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="77252-117">Вывод</span><span class="sxs-lookup"><span data-stu-id="77252-117">Output</span></span>  
 <span data-ttu-id="77252-118">Когда это возможно, выходные данные содержат исходный vtable указателя интерфейса COM.</span><span class="sxs-lookup"><span data-stu-id="77252-118">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="77252-119">В противном случае отображается информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="77252-119">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="77252-120">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="77252-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="77252-121">См. также</span><span class="sxs-lookup"><span data-stu-id="77252-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="77252-122">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="77252-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="77252-123">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="77252-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
