---
title: exceptionSwallowedOnCallFromCom MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Ексцептионсвалловедонкаллфромком в .NET. Этот MDA имеет место при возникновении исключения, но нет хорошего способа сообщить о нем.
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
ms.openlocfilehash: 11daccb4d1e757bf2fae25858d706eee5921c509
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244357"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="938ec-104">exceptionSwallowedOnCallFromCom MDA</span><span class="sxs-lookup"><span data-stu-id="938ec-104">exceptionSwallowedOnCallFromCom MDA</span></span>

<span data-ttu-id="938ec-105">Помощник отладки управляемого кода (MDA) `exceptionSwallowedOnCallFromCOM` активируется при возникновении исключения из кода среды CLR, вызываемого из COM посредством метода, который не имеет неуправляемого типа возвращаемого значения HRESULT.</span><span class="sxs-lookup"><span data-stu-id="938ec-105">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="938ec-106">Симптомы</span><span class="sxs-lookup"><span data-stu-id="938ec-106">Symptoms</span></span>  

 <span data-ttu-id="938ec-107">Вызов управляемого компонента из COM возвращает значение FALSE или 0.</span><span class="sxs-lookup"><span data-stu-id="938ec-107">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="938ec-108">Кроме того, если метод имеет тип возвращаемого значения void, указание на возникновение исключения во время выполнения метода может отсутствовать.</span><span class="sxs-lookup"><span data-stu-id="938ec-108">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="938ec-109">В этом случае исключение будет перехвачено без предупреждения и возвращено вызывающему объекту COM.</span><span class="sxs-lookup"><span data-stu-id="938ec-109">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="938ec-110">Причина:</span><span class="sxs-lookup"><span data-stu-id="938ec-110">Cause</span></span>  

 <span data-ttu-id="938ec-111">Возникло исключение, однако не существует приемлемого способа сообщить об этом.</span><span class="sxs-lookup"><span data-stu-id="938ec-111">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="938ec-112">Разрешение</span><span class="sxs-lookup"><span data-stu-id="938ec-112">Resolution</span></span>  

 <span data-ttu-id="938ec-113">Сведения приведены исключительно для справки и необязательно указывают на наличие ошибки.</span><span class="sxs-lookup"><span data-stu-id="938ec-113">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="938ec-114">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="938ec-114">Effect on the Runtime</span></span>  

 <span data-ttu-id="938ec-115">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="938ec-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="938ec-116">Он только выводит данные об исключениях, перехваченных без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="938ec-116">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="938ec-117">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="938ec-117">Output</span></span>  

 <span data-ttu-id="938ec-118">Информационное сообщение с именем метода, именем типа и указанием на исключение.</span><span class="sxs-lookup"><span data-stu-id="938ec-118">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="938ec-119">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="938ec-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="938ec-120">См. также</span><span class="sxs-lookup"><span data-stu-id="938ec-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="938ec-121">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="938ec-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="938ec-122">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="938ec-122">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
