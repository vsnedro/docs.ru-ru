---
title: Помощник по отладке управляемого кода invalidMemberDeclaration
description: Ознакомьтесь с помощником по отладке управляемого кода Инвалидмембердекларатион, который вызывается, если ошибка HRESULT возвращается в COM без вызова управляемого метода.
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: c8d6c69fc6eb4f5f690b02809fdc492da675c3b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272557"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="5ebc9-103">Помощник по отладке управляемого кода invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="5ebc9-103">invalidMemberDeclaration MDA</span></span>

<span data-ttu-id="5ebc9-104">Помощник по отладке (MDA) управляемого кода `invalidMemberDeclaration` активируется для сообщения об ошибке, которая возникает при определении способа маршалинга параметров члена, вызываемого из COM.</span><span class="sxs-lookup"><span data-stu-id="5ebc9-104">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5ebc9-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="5ebc9-105">Symptoms</span></span>  

 <span data-ttu-id="5ebc9-106">Значение HRESULT, свидетельствующее об ошибке, возвращается в COM без вызова управляемого метода.</span><span class="sxs-lookup"><span data-stu-id="5ebc9-106">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5ebc9-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="5ebc9-107">Cause</span></span>  

 <span data-ttu-id="5ebc9-108">Наиболее вероятная причина — несовместимый атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> в одном из параметров.</span><span class="sxs-lookup"><span data-stu-id="5ebc9-108">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5ebc9-109">Разрешение</span><span class="sxs-lookup"><span data-stu-id="5ebc9-109">Resolution</span></span>  

 <span data-ttu-id="5ebc9-110">Укажите допустимые атрибуты <xref:System.Runtime.InteropServices.MarshalAsAttribute> в параметрах.</span><span class="sxs-lookup"><span data-stu-id="5ebc9-110">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5ebc9-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="5ebc9-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="5ebc9-112">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="5ebc9-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5ebc9-113">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5ebc9-113">Output</span></span>  

 <span data-ttu-id="5ebc9-114">Информационное сообщение с именем члена, именем типа и сообщением об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5ebc9-114">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="5ebc9-115">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="5ebc9-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ebc9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5ebc9-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="5ebc9-117">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="5ebc9-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="5ebc9-118">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="5ebc9-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
