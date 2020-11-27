---
title: Помощник по отладке управляемого кода invalidVariant
description: Ознакомьтесь с помощником по отладке управляемого кода Инвалидвариант, который вызывается при обнаружении недопустимого варианта в вызове из машинного или неуправляемого в управляемый код.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
ms.openlocfilehash: f0667a54e950ead27000eb6b93ebd547dea1cfb0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281304"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="7c9ca-103">Помощник по отладке управляемого кода invalidVariant</span><span class="sxs-lookup"><span data-stu-id="7c9ca-103">invalidVariant MDA</span></span>

<span data-ttu-id="7c9ca-104">Помощник по отладке управляемого кода (MDA) `invalidVariant` активируется, когда во время вызова из машинного или неуправляемого кода обнаруживается недопустимая структура `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="7c9ca-104">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="7c9ca-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="7c9ca-105">Symptoms</span></span>  

 <span data-ttu-id="7c9ca-106">Непредвиденное поведение во время перехода между машинным и управляемым кодом, включающего маршалинг `VARIANT` к объекту.</span><span class="sxs-lookup"><span data-stu-id="7c9ca-106">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="7c9ca-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="7c9ca-107">Cause</span></span>  

 <span data-ttu-id="7c9ca-108">Машинный код передает в управляемый код структуру `VARIANT` неправильного формата.</span><span class="sxs-lookup"><span data-stu-id="7c9ca-108">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="7c9ca-109">Среда выполнения пытается выполнить маршалинг этой структуры `VARIANT` в объект и активирует MDA, если `VARIANT` является недопустимой.</span><span class="sxs-lookup"><span data-stu-id="7c9ca-109">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="7c9ca-110">Примеры недопустимых структур `VARIANT` включают `VARIANT` с `VARTYPE` VT_EMPTY | VT_BYREF или `VARIANT` с `VARTYPE` VT_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="7c9ca-110">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="7c9ca-111">Разрешение</span><span class="sxs-lookup"><span data-stu-id="7c9ca-111">Resolution</span></span>  

 <span data-ttu-id="7c9ca-112">Машинный или неуправляемый код, передающий `VARIANT`, должен убедиться, что структура `VARIANT` правильно сформирована и инициализирована.</span><span class="sxs-lookup"><span data-stu-id="7c9ca-112">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7c9ca-113">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="7c9ca-113">Effect on the Runtime</span></span>  

 <span data-ttu-id="7c9ca-114">MDA не оказывает влияния на поведение среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="7c9ca-114">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7c9ca-115">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7c9ca-115">Output</span></span>  

 <span data-ttu-id="7c9ca-116">Сообщение MDA, указывающее, что среда выполнения обнаружила недопустимую структуру `VARIANT`, переданную в управляемый код неуправляемым модулем.</span><span class="sxs-lookup"><span data-stu-id="7c9ca-116">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7c9ca-117">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="7c9ca-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c9ca-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7c9ca-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="7c9ca-119">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="7c9ca-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7c9ca-120">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="7c9ca-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
