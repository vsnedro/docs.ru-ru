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
ms.openlocfilehash: 65d704463ed746390ff1710b590bf080013bf53d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051731"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="049b2-103">Помощник по отладке управляемого кода invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="049b2-103">invalidIUnknown MDA</span></span>
<span data-ttu-id="049b2-104">Помощник по отладке управляемого кода (MDA) `invalidIUnknown` активируется, когда недопустимый указатель `IUnknown` передается в управляемый код из машинного кода.</span><span class="sxs-lookup"><span data-stu-id="049b2-104">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="049b2-105">`IUnknown` не удалось возвратить успех при запросе для интерфейса `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="049b2-105">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="049b2-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="049b2-106">Symptoms</span></span>  
 <span data-ttu-id="049b2-107">Непредвиденная ошибка при маршалинге указателя интерфейса СОМ во время маршалинга аргумента.</span><span class="sxs-lookup"><span data-stu-id="049b2-107">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="049b2-108">Причина:</span><span class="sxs-lookup"><span data-stu-id="049b2-108">Cause</span></span>  
 <span data-ttu-id="049b2-109">Неверная реализация `QueryInterface` в интерфейсе COM, переданном в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="049b2-109">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="049b2-110">Решение</span><span class="sxs-lookup"><span data-stu-id="049b2-110">Resolution</span></span>  
 <span data-ttu-id="049b2-111">Исправьте реализацию `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="049b2-111">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="049b2-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="049b2-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="049b2-113">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="049b2-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="049b2-114">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="049b2-114">Output</span></span>  
 <span data-ttu-id="049b2-115">Описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="049b2-115">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="049b2-116">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="049b2-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="049b2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="049b2-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="049b2-118">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="049b2-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="049b2-119">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="049b2-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
