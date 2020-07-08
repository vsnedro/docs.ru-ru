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
ms.openlocfilehash: 5dbfba2baec3263d91746c06379438e97a81f005
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051718"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="e0943-103">Помощник по отладке управляемого кода invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="e0943-103">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="e0943-104">Помощник по отладке (MDA) управляемого кода `invalidMemberDeclaration` активируется для сообщения об ошибке, которая возникает при определении способа маршалинга параметров члена, вызываемого из COM.</span><span class="sxs-lookup"><span data-stu-id="e0943-104">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e0943-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="e0943-105">Symptoms</span></span>  
 <span data-ttu-id="e0943-106">Значение HRESULT, свидетельствующее об ошибке, возвращается в COM без вызова управляемого метода.</span><span class="sxs-lookup"><span data-stu-id="e0943-106">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e0943-107">Причина:</span><span class="sxs-lookup"><span data-stu-id="e0943-107">Cause</span></span>  
 <span data-ttu-id="e0943-108">Наиболее вероятная причина — несовместимый атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> в одном из параметров.</span><span class="sxs-lookup"><span data-stu-id="e0943-108">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e0943-109">Решение</span><span class="sxs-lookup"><span data-stu-id="e0943-109">Resolution</span></span>  
 <span data-ttu-id="e0943-110">Укажите допустимые атрибуты <xref:System.Runtime.InteropServices.MarshalAsAttribute> в параметрах.</span><span class="sxs-lookup"><span data-stu-id="e0943-110">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e0943-111">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="e0943-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="e0943-112">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="e0943-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e0943-113">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e0943-113">Output</span></span>  
 <span data-ttu-id="e0943-114">Информационное сообщение с именем члена, именем типа и сообщением об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e0943-114">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e0943-115">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="e0943-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0943-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e0943-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="e0943-117">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="e0943-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="e0943-118">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="e0943-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
