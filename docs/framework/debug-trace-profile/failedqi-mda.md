---
title: Помощник по отладке управляемого кода failedQI
description: Ознакомьтесь с помощником по отладке управляемого кода (MDA) Фаиледки в .NET, который может быть активирован при сбое приведения или вызове COM из вызываемой оболочки времени выполнения (RCW).
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
ms.openlocfilehash: bbd8d5644f8620444d80845b9920b925b6891176
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244331"
---
# <a name="failedqi-mda"></a><span data-ttu-id="f1a9d-103">Помощник по отладке управляемого кода failedQI</span><span class="sxs-lookup"><span data-stu-id="f1a9d-103">failedQI MDA</span></span>

<span data-ttu-id="f1a9d-104">Помощник по отладке управляемого кода (MDA) `failedQI` активируется, когда среда выполнения вызывает `QueryInterface`в указателе интерфейса СОМ от имени вызываемой оболочки времени выполнения (RCW), и вызов `QueryInterface` завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-104">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f1a9d-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="f1a9d-105">Symptoms</span></span>  

 <span data-ttu-id="f1a9d-106">Произошел сбой приведения в RCW, или вызов COM из RCW неожиданно завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-106">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f1a9d-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="f1a9d-107">Cause</span></span>  
  
- <span data-ttu-id="f1a9d-108">Вызов выполняется из неправильного контекста.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-108">The call is made from the wrong context.</span></span>  
  
- <span data-ttu-id="f1a9d-109">Зарегистрированному прокси-серверу не удается выполнить вызов `QueryInterface`, поскольку вызов выполнялся из неправильного контекста.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-109">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
- <span data-ttu-id="f1a9d-110">Прокси-сервер, принадлежащий OLE, возвратил значение HRESULT, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-110">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f1a9d-111">Разрешение</span><span class="sxs-lookup"><span data-stu-id="f1a9d-111">Resolution</span></span>  

 <span data-ttu-id="f1a9d-112">Правила COM см. в документации MSDN.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-112">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f1a9d-113">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="f1a9d-113">Effect on the Runtime</span></span>  

 <span data-ttu-id="f1a9d-114">Если вызов `QueryInterface` завершается с ошибкой, контекст переключается и предпринимается попытка повторно выполнить вызов `QueryInterface`, чтобы увидеть, не использовался ли при сбое неправильный контекст.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-114">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f1a9d-115">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f1a9d-115">Output</span></span>  

 <span data-ttu-id="f1a9d-116">Управляемое имя интерфейса, идентификатор GUID интерфейса и значение HRESULT ошибки.</span><span class="sxs-lookup"><span data-stu-id="f1a9d-116">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f1a9d-117">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="f1a9d-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1a9d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f1a9d-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f1a9d-119">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="f1a9d-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f1a9d-120">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="f1a9d-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
