---
title: notMarshalable MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Нотмаршалабле, который может активироваться, если вызовы не обслуживаются или происходят в неправильном контексте для указателей на интерфейсы COM.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
ms.openlocfilehash: 344c275d8645b16de3ecb06517297df06323ced4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254562"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="a1605-103">notMarshalable MDA</span><span class="sxs-lookup"><span data-stu-id="a1605-103">notMarshalable MDA</span></span>

<span data-ttu-id="a1605-104">Помощник по отладке (MDA) управляемого кода `notMarshalable` активируется, когда среда CLR обнаруживает указатель интерфейса СОМ без допустимого зарегистрированного прокси или заглушки или неправильную реализацию интерфейса `IMarshal` при попытке выполнить маршалинг интерфейса по контекстам.</span><span class="sxs-lookup"><span data-stu-id="a1605-104">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a1605-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="a1605-105">Symptoms</span></span>  

 <span data-ttu-id="a1605-106">Вызовы не обслуживаются, или вызовы выполняются из неправильного контекста для указателей интерфейса СОМ.</span><span class="sxs-lookup"><span data-stu-id="a1605-106">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a1605-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="a1605-107">Cause</span></span>  

 <span data-ttu-id="a1605-108">Отсутствует допустимый зарегистрированный прокси или заглушка, или неправильный `IMarshal` при попытке выполнить маршалинг интерфейса по контекстам.</span><span class="sxs-lookup"><span data-stu-id="a1605-108">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a1605-109">Разрешение</span><span class="sxs-lookup"><span data-stu-id="a1605-109">Resolution</span></span>  

 <span data-ttu-id="a1605-110">Убедитесь, что имеются зарегистрированный прокси или заглушка и что реализация `IMarshal` является допустимой.</span><span class="sxs-lookup"><span data-stu-id="a1605-110">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a1605-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="a1605-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="a1605-112">Этот MDA не оказывает никакого влияния на среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="a1605-112">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a1605-113">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a1605-113">Output</span></span>  

 <span data-ttu-id="a1605-114">Сообщение, описывающее проблему.</span><span class="sxs-lookup"><span data-stu-id="a1605-114">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a1605-115">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="a1605-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1605-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a1605-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="a1605-117">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="a1605-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="a1605-118">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="a1605-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
