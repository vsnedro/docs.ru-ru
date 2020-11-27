---
title: Помощник по отладке управляемого кода invalidIUnknown
description: Ознакомьтесь с помощником по отладке управляемого кода Инвалидиункновн (MDA), который активируется при передаче недействительного указателя IUnknown в управляемый код из машинного кода.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 8e7ca6c9c43c4f507d235c879498b2e831c6eba9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272544"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="b2d17-103">Помощник по отладке управляемого кода invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="b2d17-103">invalidIUnknown MDA</span></span>

<span data-ttu-id="b2d17-104">Помощник по отладке управляемого кода (MDA) `invalidIUnknown` активируется, когда недопустимый указатель `IUnknown` передается в управляемый код из машинного кода.</span><span class="sxs-lookup"><span data-stu-id="b2d17-104">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="b2d17-105">`IUnknown` не удалось возвратить успех при запросе для интерфейса `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="b2d17-105">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b2d17-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="b2d17-106">Symptoms</span></span>  

 <span data-ttu-id="b2d17-107">Непредвиденная ошибка при маршалинге указателя интерфейса СОМ во время маршалинга аргумента.</span><span class="sxs-lookup"><span data-stu-id="b2d17-107">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b2d17-108">Причина:</span><span class="sxs-lookup"><span data-stu-id="b2d17-108">Cause</span></span>  

 <span data-ttu-id="b2d17-109">Неверная реализация `QueryInterface` в интерфейсе COM, переданном в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="b2d17-109">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b2d17-110">Разрешение</span><span class="sxs-lookup"><span data-stu-id="b2d17-110">Resolution</span></span>  

 <span data-ttu-id="b2d17-111">Исправьте реализацию `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="b2d17-111">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b2d17-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="b2d17-112">Effect on the Runtime</span></span>  

 <span data-ttu-id="b2d17-113">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="b2d17-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b2d17-114">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b2d17-114">Output</span></span>  

 <span data-ttu-id="b2d17-115">Описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="b2d17-115">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b2d17-116">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="b2d17-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2d17-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b2d17-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="b2d17-118">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="b2d17-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b2d17-119">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="b2d17-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
