---
title: Помощник по отладке управляемого кода pInvokeLog
description: Изучите помощник по отладке управляемого кода Пинвокелог (MDA), который активируется для каждой уникальной сигнатуры вызова платформы, используемой во время выполнения в .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
ms.openlocfilehash: 05af4e17a91f7c0d8f3576a86d3d784ef6666aed
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803694"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="2f5da-103">Помощник по отладке управляемого кода pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="2f5da-103">pInvokeLog MDA</span></span>
<span data-ttu-id="2f5da-104">Помощник по отладке управляемого кода `pInvokeLog` активируется для каждой уникальной сигнатуры вызова неуправляемого кода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2f5da-104">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="2f5da-105">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="2f5da-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="2f5da-106">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="2f5da-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="2f5da-107">Вывод</span><span class="sxs-lookup"><span data-stu-id="2f5da-107">Output</span></span>  
 <span data-ttu-id="2f5da-108">Сообщение, указывающее на сигнатуру вызова неуправляемого кода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2f5da-108">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="2f5da-109">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="2f5da-109">Configuration</span></span>  
 <span data-ttu-id="2f5da-110">Каждый совпадающий элемент фильтрует DLL-файлы, к которым выполняются вызовы неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="2f5da-110">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f5da-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2f5da-111">See also</span></span>

- [<span data-ttu-id="2f5da-112">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="2f5da-112">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="2f5da-113">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="2f5da-113">Consuming Unmanaged DLL Functions</span></span>](../interop/consuming-unmanaged-dll-functions.md)
