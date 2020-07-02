---
title: pInvokeStackImbalance MDA
description: Ознакомьтесь с MDA Пинвокестаккимбаланце, который может быть активирован во время нарушения прав доступа или повреждения памяти при вызове или после вызова неуправляемого кода.
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
ms.openlocfilehash: 89afd3fce3f2a8bffe88d45991ceeb59fc5e5b76
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803668"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="6b1b7-103">PInvokeStackImbalance MDA</span><span class="sxs-lookup"><span data-stu-id="6b1b7-103">PInvokeStackImbalance MDA</span></span>

<span data-ttu-id="6b1b7-104">`PInvokeStackImbalance`Помощник по отладке управляемого кода (MDA) активируется, когда среда CLR обнаруживает, что глубина стека после вызова неуправляемого кода не совпадает с ожидаемой глубиной стека, учитывая соглашение о вызовах, указанное в <xref:System.Runtime.InteropServices.DllImportAttribute> атрибуте, и объявление параметров в управляемой сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-104">The `PInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute and the declaration of the parameters in the managed signature.</span></span>

<span data-ttu-id="6b1b7-105">MDA `PInvokeStackImbalance` реализован только для 32-разрядных платформ x86.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-105">The `PInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="6b1b7-106">По `PInvokeStackImbalance` умолчанию MDA отключен.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-106">The `PInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="6b1b7-107">В Visual Studio 2017 и более поздних версиях `PInvokeStackImbalance` MDA отображается в списке **помощники по отладке управляемого** кода в диалоговом окне **параметры исключений** (которое отображается при выборе параметра **Отладка**  >  **Windows**  >  **параметров исключений**Windows).</span><span class="sxs-lookup"><span data-stu-id="6b1b7-107">In Visual Studio 2017 and later versions, the `PInvokeStackImbalance` MDA appears in the **Managed Debugging Assistants** list in the **Exception Settings** dialog box (which is displayed when you select **Debug** > **Windows** > **Exception Settings**).</span></span> <span data-ttu-id="6b1b7-108">Однако установка или снятие флажка **прерывать при возникновении** не включает и не отключает MDA. Он только определяет, создает ли Visual Studio исключение при активации MDA.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-108">However, selecting or clearing the **Break When Thrown** check box does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>

## <a name="symptoms"></a><span data-ttu-id="6b1b7-109">Симптомы</span><span class="sxs-lookup"><span data-stu-id="6b1b7-109">Symptoms</span></span>

<span data-ttu-id="6b1b7-110">В приложении обнаружено нарушение прав доступа или повреждение памяти при выполнении или отслеживании вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-110">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>

## <a name="cause"></a><span data-ttu-id="6b1b7-111">Причина</span><span class="sxs-lookup"><span data-stu-id="6b1b7-111">Cause</span></span>

<span data-ttu-id="6b1b7-112">Управляемая сигнатура вызова неуправляемого кода может не соответствовать неуправляемой сигнатуре вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-112">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="6b1b7-113">Это несоответствие может быть вызвано тем, что управляемая сигнатура не объявляет правильное количество параметров или не задает соответствующий размер для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-113">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="6b1b7-114">MDA также может активироваться, поскольку соглашение о вызовах, возможно указанное атрибутом <xref:System.Runtime.InteropServices.DllImportAttribute>, не соответствует соглашению о вызовах неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-114">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>

## <a name="resolution"></a><span data-ttu-id="6b1b7-115">Решение</span><span class="sxs-lookup"><span data-stu-id="6b1b7-115">Resolution</span></span>

<span data-ttu-id="6b1b7-116">Просмотрите сигнатуру вызова неуправляемого кода и соглашение о вызовах, чтобы убедиться, что они соответствуют сигнатуре и соглашению о вызовах исходного целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-116">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="6b1b7-117">Попробуйте явным образом задать соглашение о вызовах для управляемой и неуправляемой сторон.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-117">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="6b1b7-118">Также возможно, хотя и маловероятно, что неуправляемая функция внесла дисбаланс в стек по какой-либо другой причине, например из-за ошибки в неуправляемом компиляторе.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-118">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="6b1b7-119">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="6b1b7-119">Effect on the Runtime</span></span>

<span data-ttu-id="6b1b7-120">Заставляет все вызовы неуправляемого кода принимать неоптимизированный путь в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-120">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="6b1b7-121">Вывод</span><span class="sxs-lookup"><span data-stu-id="6b1b7-121">Output</span></span>

<span data-ttu-id="6b1b7-122">Сообщение MDA предоставляет имя вызова метода вызова неуправляемого кода, который привел к несбалансированности стека вызова.</span><span class="sxs-lookup"><span data-stu-id="6b1b7-122">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span> <span data-ttu-id="6b1b7-123">Пример сообщения вызова неуправляемого кода в методе `SampleMethod`:</span><span class="sxs-lookup"><span data-stu-id="6b1b7-123">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>

<span data-ttu-id="6b1b7-124">**Вызов функции PInvoke "SampleMethod" не сбалансирован стек. Скорее всего, это связано с тем, что управляемая сигнатура PInvoke не соответствует неуправляемой сигнатуре целевого объекта. Убедитесь, что соглашение о вызовах и параметры сигнатуры PInvoke соответствуют целевой неуправляемой подписи.**</span><span class="sxs-lookup"><span data-stu-id="6b1b7-124">**A call to PInvoke function 'SampleMethod' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="configuration"></a><span data-ttu-id="6b1b7-125">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="6b1b7-125">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="6b1b7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="6b1b7-126">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="6b1b7-127">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="6b1b7-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6b1b7-128">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="6b1b7-128">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
