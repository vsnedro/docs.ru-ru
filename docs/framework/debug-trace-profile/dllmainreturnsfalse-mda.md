---
title: Помощник по отладке управляемого кода dllMainReturnsFalse
description: Ознакомьтесь с помощником по отладке управляемого кода Дллмаинретурнсфалсе в .NET. Этот MDA активируется при сбое инициализации DLL.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
ms.openlocfilehash: 21d5e37d6823876e07cf5b2cbb881c1cf8b47b11
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416061"
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="72475-104">Помощник по отладке управляемого кода dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="72475-104">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="72475-105">Помощник по отладке управляемого кода `dllMainReturnsFalse` (MDA) активируется в том случае, если управляемая функция `DllMain` в пользовательской сборке вызывается с причиной DLL_PROCESS_ATTACH и возвращает значение FALSE.</span><span class="sxs-lookup"><span data-stu-id="72475-105">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="72475-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="72475-106">Symptoms</span></span>  
 <span data-ttu-id="72475-107">Функция `DllMain` возвращает значение FALSE, свидетельствующее о сбое при ее выполнении.</span><span class="sxs-lookup"><span data-stu-id="72475-107">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="72475-108">Это может привести к возникновению неопределенных проблем, поскольку функции `DllMain` обычно содержат важный код инициализации.</span><span class="sxs-lookup"><span data-stu-id="72475-108">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="72475-109">Причина</span><span class="sxs-lookup"><span data-stu-id="72475-109">Cause</span></span>  
 <span data-ttu-id="72475-110">Функция `DllMain` вызывается с причиной DLL_PROCESS_ATTACH для инициализации библиотеки DLL при загрузке.</span><span class="sxs-lookup"><span data-stu-id="72475-110">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="72475-111">Если она возвращает значение FALSE, значит инициализация библиотеки DLL завершилась сбоем.</span><span class="sxs-lookup"><span data-stu-id="72475-111">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="72475-112">Решение</span><span class="sxs-lookup"><span data-stu-id="72475-112">Resolution</span></span>  
 <span data-ttu-id="72475-113">Проанализируйте код функции `DllMain` для указанной библиотеки DLL и определите причину сбоя при инициализации.</span><span class="sxs-lookup"><span data-stu-id="72475-113">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="72475-114">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="72475-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="72475-115">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="72475-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="72475-116">Он только выводит данные о возвращаемом значении для `DllMain`.</span><span class="sxs-lookup"><span data-stu-id="72475-116">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="72475-117">Вывод</span><span class="sxs-lookup"><span data-stu-id="72475-117">Output</span></span>  
 <span data-ttu-id="72475-118">Сообщение, указывающее, что функция `DllMain` была вызвана с причиной DLL_PROCESS_ATTACH и вернула значение FALSE.</span><span class="sxs-lookup"><span data-stu-id="72475-118">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="72475-119">Обратите внимание, что этот помощник по отладке кода вызывается только в том случае, если в управляемом коде реализована функция `DllMain`.</span><span class="sxs-lookup"><span data-stu-id="72475-119">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="72475-120">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="72475-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72475-121">См. также</span><span class="sxs-lookup"><span data-stu-id="72475-121">See also</span></span>

- [<span data-ttu-id="72475-122">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="72475-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
