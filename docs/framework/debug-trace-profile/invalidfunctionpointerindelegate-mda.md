---
title: invalidFunctionPointerInDelegate MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Инвалидфунктионпоинтеринделегате (MDA), который вызывается, если передается недопустимый указатель на функцию для создания делегата.
ms.date: 03/30/2017
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
ms.openlocfilehash: a17427d117c62ba782af3c9549c84623a3013b06
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051744"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="d72e0-103">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="d72e0-103">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="d72e0-104">Помощник отладки управляемого кода `invalidFunctionPointerInDelegate` (MDA) активируется, когда передается недопустимый указатель функции для создания делегата поверх собственного указателя функции.</span><span class="sxs-lookup"><span data-stu-id="d72e0-104">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d72e0-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="d72e0-105">Symptoms</span></span>  
 <span data-ttu-id="d72e0-106">Нарушения прав доступа или непредвиденное повреждение памяти при использовании делегата поверх указателя функции.</span><span class="sxs-lookup"><span data-stu-id="d72e0-106">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d72e0-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="d72e0-107">Cause</span></span>  
 <span data-ttu-id="d72e0-108">Был указан недопустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="d72e0-108">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d72e0-109">Решение</span><span class="sxs-lookup"><span data-stu-id="d72e0-109">Resolution</span></span>  
 <span data-ttu-id="d72e0-110">Укажите допустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="d72e0-110">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d72e0-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="d72e0-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="d72e0-112">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="d72e0-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d72e0-113">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d72e0-113">Output</span></span>  
 <span data-ttu-id="d72e0-114">Недопустимый указатель функции.</span><span class="sxs-lookup"><span data-stu-id="d72e0-114">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d72e0-115">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="d72e0-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d72e0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d72e0-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="d72e0-117">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="d72e0-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="d72e0-118">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="d72e0-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
