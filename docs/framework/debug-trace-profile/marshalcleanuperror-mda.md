---
title: marshalCleanupError MDA
description: Изучите помощник по отладке управляемого кода Маршалклеануперрор (MDA), который вызывается из-за непредвиденной ошибки при очистке временных структур.
ms.date: 03/30/2017
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
ms.openlocfilehash: 3c7498d6f51484de3a2e84d611a2634f53724ab6
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051615"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="6cc92-103">marshalCleanupError MDA</span><span class="sxs-lookup"><span data-stu-id="6cc92-103">marshalCleanupError MDA</span></span>
<span data-ttu-id="6cc92-104">Помощник отладки управляемого кода (MDA) `marshalCleanupError` активируется, когда при попытке очистить временные структуры и память, используемые для маршалинга типов данных между границами машинного и управляемого кода, в среде CLR возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="6cc92-104">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="6cc92-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="6cc92-105">Symptoms</span></span>  
 <span data-ttu-id="6cc92-106">При переходах между машинным и управляемым кодом возникает утечка памяти, не восстанавливается состояние среды, например культура потока, либо возникают ошибки при очистке <xref:System.Runtime.InteropServices.SafeHandle>.</span><span class="sxs-lookup"><span data-stu-id="6cc92-106">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="6cc92-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="6cc92-107">Cause</span></span>  
 <span data-ttu-id="6cc92-108">Во время очистки временных структур возникла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="6cc92-108">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="6cc92-109">Решение</span><span class="sxs-lookup"><span data-stu-id="6cc92-109">Resolution</span></span>  
 <span data-ttu-id="6cc92-110">Проверьте все реализации деструктора <xref:System.Runtime.InteropServices.SafeHandle>, метода завершения и особого упаковщика на наличие ошибок.</span><span class="sxs-lookup"><span data-stu-id="6cc92-110">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6cc92-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="6cc92-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="6cc92-112">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="6cc92-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6cc92-113">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6cc92-113">Output</span></span>  
 <span data-ttu-id="6cc92-114">Сообщение с указанием операции, завершившейся со сбоем во время очистки.</span><span class="sxs-lookup"><span data-stu-id="6cc92-114">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="6cc92-115">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="6cc92-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6cc92-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6cc92-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="6cc92-117">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="6cc92-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6cc92-118">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="6cc92-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
