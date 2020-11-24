---
title: Перечисление CorDebugInterfaceVersion
ms.date: 03/30/2017
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
ms.openlocfilehash: 939400fcc40edd62532d459d6ed626dbdc4f41fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675312"
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="2f633-102">Перечисление CorDebugInterfaceVersion</span><span class="sxs-lookup"><span data-stu-id="2f633-102">CorDebugInterfaceVersion Enumeration</span></span>

<span data-ttu-id="2f633-103">Указывает интерфейс, версию платформы .NET Framework или версию платформы .NET Framework, в которой был представлен интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2f633-103">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f633-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f633-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a><span data-ttu-id="2f633-105">Члены</span><span class="sxs-lookup"><span data-stu-id="2f633-105">Members</span></span>  

 <span data-ttu-id="2f633-106">В следующей таблице каждое значение перечисления сопоставляется с соответствующим интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="2f633-106">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="2f633-107">Кроме того, в таблице указана первая версия платформы .NET Framework, в которой поддерживался интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2f633-107">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="2f633-108">Член</span><span class="sxs-lookup"><span data-stu-id="2f633-108">Member</span></span>|<span data-ttu-id="2f633-109">Что определяет</span><span class="sxs-lookup"><span data-stu-id="2f633-109">Specifies</span></span>|<span data-ttu-id="2f633-110">Версия платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2f633-110">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="2f633-111">Недопустимая версия платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f633-111">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="2f633-112">Версия платформы .NET Framework (включая все пакеты обновления) — 1.0.</span><span class="sxs-lookup"><span data-stu-id="2f633-112">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="2f633-113">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-113">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="2f633-114">Версия платформы .NET Framework (включая все пакеты обновления) — 1.1.</span><span class="sxs-lookup"><span data-stu-id="2f633-114">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="2f633-115">1.1</span><span class="sxs-lookup"><span data-stu-id="2f633-115">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="2f633-116">Версия платформы .NET Framework (включая все пакеты обновления) — 2.0.</span><span class="sxs-lookup"><span data-stu-id="2f633-116">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="2f633-117">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-117">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="2f633-118">Версия платформы .NET Framework (включая все пакеты обновления) — 4.</span><span class="sxs-lookup"><span data-stu-id="2f633-118">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="2f633-119">4</span><span class="sxs-lookup"><span data-stu-id="2f633-119">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="2f633-120">Версия платформы .NET Framework (включая все пакеты обновления) — 4.5.</span><span class="sxs-lookup"><span data-stu-id="2f633-120">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="2f633-121">4,5</span><span class="sxs-lookup"><span data-stu-id="2f633-121">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="2f633-122">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="2f633-122">ICorDebugManagedCallback</span></span>](icordebugmanagedcallback-interface.md)|<span data-ttu-id="2f633-123">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-123">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="2f633-124">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="2f633-124">ICorDebugUnmanagedCallback</span></span>](icordebugunmanagedcallback-interface.md)|<span data-ttu-id="2f633-125">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-125">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="2f633-126">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="2f633-126">ICorDebug</span></span>](icordebug-interface.md)|<span data-ttu-id="2f633-127">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-127">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="2f633-128">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="2f633-128">ICorDebugController</span></span>](icordebugcontroller-interface.md)|<span data-ttu-id="2f633-129">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-129">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="2f633-130">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="2f633-130">ICorDebugAppDomain</span></span>](icordebugappdomain-interface.md)|<span data-ttu-id="2f633-131">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-131">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="2f633-132">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="2f633-132">ICorDebugAssembly</span></span>](icordebugassembly-interface.md)|<span data-ttu-id="2f633-133">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-133">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="2f633-134">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="2f633-134">ICorDebugProcess</span></span>](icordebugprocess-interface.md)|<span data-ttu-id="2f633-135">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-135">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="2f633-136">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2f633-136">ICorDebugBreakpoint</span></span>](icordebugbreakpoint-interface.md)|<span data-ttu-id="2f633-137">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-137">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="2f633-138">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2f633-138">ICorDebugFunctionBreakpoint</span></span>](icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="2f633-139">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-139">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="2f633-140">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2f633-140">ICorDebugModuleBreakpoint</span></span>](icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="2f633-141">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-141">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="2f633-142">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2f633-142">ICorDebugValueBreakpoint</span></span>](icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="2f633-143">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-143">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="2f633-144">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="2f633-144">ICorDebugStepper</span></span>](icordebugstepper-interface.md)|<span data-ttu-id="2f633-145">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-145">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="2f633-146">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="2f633-146">ICorDebugRegisterSet</span></span>](icordebugregisterset-interface.md)|<span data-ttu-id="2f633-147">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-147">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="2f633-148">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="2f633-148">ICorDebugThread</span></span>](icordebugthread-interface.md)|<span data-ttu-id="2f633-149">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-149">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="2f633-150">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="2f633-150">ICorDebugChain</span></span>](icordebugchain-interface.md)|<span data-ttu-id="2f633-151">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-151">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="2f633-152">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="2f633-152">ICorDebugFrame</span></span>](icordebugframe-interface.md)|<span data-ttu-id="2f633-153">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-153">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="2f633-154">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="2f633-154">ICorDebugILFrame</span></span>](icordebugilframe-interface.md)|<span data-ttu-id="2f633-155">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-155">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="2f633-156">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="2f633-156">ICorDebugNativeFrame</span></span>](icordebugnativeframe-interface.md)|<span data-ttu-id="2f633-157">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-157">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="2f633-158">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="2f633-158">ICorDebugModule</span></span>](icordebugmodule-interface.md)|<span data-ttu-id="2f633-159">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-159">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="2f633-160">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="2f633-160">ICorDebugFunction</span></span>](icordebugfunction-interface1.md)|<span data-ttu-id="2f633-161">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-161">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="2f633-162">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="2f633-162">ICorDebugCode</span></span>](icordebugcode-interface1.md)|<span data-ttu-id="2f633-163">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-163">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="2f633-164">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="2f633-164">ICorDebugClass</span></span>](icordebugclass-interface.md)|<span data-ttu-id="2f633-165">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-165">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="2f633-166">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="2f633-166">ICorDebugEval</span></span>](icordebugeval-interface.md)|<span data-ttu-id="2f633-167">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-167">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="2f633-168">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="2f633-168">ICorDebugValue</span></span>](icordebugvalue-interface.md)|<span data-ttu-id="2f633-169">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-169">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="2f633-170">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="2f633-170">ICorDebugGenericValue</span></span>](icordebuggenericvalue-interface.md)|<span data-ttu-id="2f633-171">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-171">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="2f633-172">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="2f633-172">ICorDebugReferenceValue</span></span>](icordebugreferencevalue-interface.md)|<span data-ttu-id="2f633-173">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-173">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="2f633-174">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="2f633-174">ICorDebugHeapValue</span></span>](icordebugheapvalue-interface.md)|<span data-ttu-id="2f633-175">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-175">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="2f633-176">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="2f633-176">ICorDebugObjectValue</span></span>](icordebugobjectvalue-interface.md)|<span data-ttu-id="2f633-177">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-177">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="2f633-178">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="2f633-178">ICorDebugBoxValue</span></span>](icordebugboxvalue-interface.md)|<span data-ttu-id="2f633-179">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-179">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="2f633-180">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="2f633-180">ICorDebugStringValue</span></span>](icordebugstringvalue-interface.md)|<span data-ttu-id="2f633-181">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-181">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="2f633-182">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="2f633-182">ICorDebugArrayValue</span></span>](icordebugarrayvalue-interface.md)|<span data-ttu-id="2f633-183">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-183">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="2f633-184">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="2f633-184">ICorDebugContext</span></span>](icordebugcontext-interface.md)|<span data-ttu-id="2f633-185">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-185">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="2f633-186">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-186">ICorDebugEnum</span></span>](icordebugenum-interface1.md)|<span data-ttu-id="2f633-187">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-187">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="2f633-188">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-188">ICorDebugObjectEnum</span></span>](icordebugobjectenum-interface.md)|<span data-ttu-id="2f633-189">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-189">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="2f633-190">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-190">ICorDebugBreakpointEnum</span></span>](icordebugbreakpointenum-interface.md)|<span data-ttu-id="2f633-191">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-191">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="2f633-192">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-192">ICorDebugStepperEnum</span></span>](icordebugstepperenum-interface.md)|<span data-ttu-id="2f633-193">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-193">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="2f633-194">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-194">ICorDebugProcessEnum</span></span>](icordebugprocessenum-interface.md)|<span data-ttu-id="2f633-195">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-195">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="2f633-196">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-196">ICorDebugThreadEnum</span></span>](icordebugthreadenum-interface1.md)|<span data-ttu-id="2f633-197">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-197">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="2f633-198">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-198">ICorDebugFrameEnum</span></span>](icordebugframeenum-interface.md)|<span data-ttu-id="2f633-199">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-199">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="2f633-200">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-200">ICorDebugChainEnum</span></span>](icordebugchainenum-interface.md)|<span data-ttu-id="2f633-201">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-201">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="2f633-202">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-202">ICorDebugModuleEnum</span></span>](icordebugmoduleenum-interface.md)|<span data-ttu-id="2f633-203">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-203">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="2f633-204">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-204">ICorDebugValueEnum</span></span>](icordebugvalueenum-interface.md)|<span data-ttu-id="2f633-205">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-205">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="2f633-206">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-206">ICorDebugCodeEnum</span></span>](icordebugcodeenum-interface.md)|<span data-ttu-id="2f633-207">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-207">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="2f633-208">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-208">ICorDebugTypeEnum</span></span>](icordebugtypeenum-interface.md)|<span data-ttu-id="2f633-209">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-209">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="2f633-210">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-210">ICorDebugErrorInfoEnum</span></span>](icordebugerrorinfoenum-interface.md)|<span data-ttu-id="2f633-211">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-211">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="2f633-212">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-212">ICorDebugAppDomainEnum</span></span>](icordebugappdomainenum-interface.md)|<span data-ttu-id="2f633-213">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-213">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="2f633-214">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-214">ICorDebugAssemblyEnum</span></span>](icordebugassemblyenum-interface.md)|<span data-ttu-id="2f633-215">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-215">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="2f633-216">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="2f633-216">ICorDebugEditAndContinueErrorInfo</span></span>](icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="2f633-217">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-217">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="2f633-218">Метод icordebugeditandcontinuesnapshot</span><span class="sxs-lookup"><span data-stu-id="2f633-218">ICorDebugEditAndContinueSnapshot</span></span>](icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="2f633-219">1.0</span><span class="sxs-lookup"><span data-stu-id="2f633-219">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="2f633-220">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="2f633-220">ICorDebugManagedCallback2</span></span>](icordebugmanagedcallback2-interface.md)|<span data-ttu-id="2f633-221">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-221">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="2f633-222">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="2f633-222">ICorDebugAppDomain2</span></span>](icordebugappdomain2-interface.md)|<span data-ttu-id="2f633-223">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-223">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="2f633-224">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="2f633-224">ICorDebugProcess2</span></span>](icordebugprocess2-interface1.md)|<span data-ttu-id="2f633-225">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-225">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="2f633-226">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="2f633-226">ICorDebugStepper2</span></span>](icordebugstepper2-interface1.md)|<span data-ttu-id="2f633-227">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-227">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="2f633-228">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="2f633-228">ICorDebugRegisterSet2</span></span>](icordebugregisterset2-interface.md)|<span data-ttu-id="2f633-229">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-229">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="2f633-230">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="2f633-230">ICorDebugThread2</span></span>](icordebugthread2-interface.md)|<span data-ttu-id="2f633-231">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-231">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="2f633-232">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="2f633-232">ICorDebugILFrame2</span></span>](icordebugilframe2-interface.md)|<span data-ttu-id="2f633-233">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-233">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="2f633-234">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="2f633-234">ICorDebugModule2</span></span>](icordebugmodule2-interface.md)|<span data-ttu-id="2f633-235">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-235">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="2f633-236">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="2f633-236">ICorDebugFunction2</span></span>](icordebugfunction2-interface.md)|<span data-ttu-id="2f633-237">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-237">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="2f633-238">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="2f633-238">ICorDebugCode2</span></span>](icordebugcode2-interface.md)|<span data-ttu-id="2f633-239">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-239">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="2f633-240">ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="2f633-240">"ICorDebugClass2"</span></span>|<span data-ttu-id="2f633-241">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-241">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="2f633-242">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="2f633-242">"ICorDebugValue2"</span></span>|<span data-ttu-id="2f633-243">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-243">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="2f633-244">"ICorDebugEval2".</span><span class="sxs-lookup"><span data-stu-id="2f633-244">The "ICorDebugEval2".</span></span>|<span data-ttu-id="2f633-245">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-245">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="2f633-246">ICorDebugObjectValue2</span><span class="sxs-lookup"><span data-stu-id="2f633-246">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="2f633-247">2.0</span><span class="sxs-lookup"><span data-stu-id="2f633-247">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="2f633-248">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="2f633-248">ICorDebugThread3</span></span>](icordebugthread3-interface.md)|<span data-ttu-id="2f633-249">4</span><span class="sxs-lookup"><span data-stu-id="2f633-249">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="2f633-250">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="2f633-250">ICorDebugThread4</span></span>](icordebugthread4-interface.md)|<span data-ttu-id="2f633-251">4</span><span class="sxs-lookup"><span data-stu-id="2f633-251">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="2f633-252">ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="2f633-252">ICorDebugStackWalk</span></span>](icordebugstackwalk-interface.md)|<span data-ttu-id="2f633-253">4</span><span class="sxs-lookup"><span data-stu-id="2f633-253">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="2f633-254">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="2f633-254">ICorDebugNativeFrame2</span></span>](icordebugnativeframe2-interface.md)|<span data-ttu-id="2f633-255">4</span><span class="sxs-lookup"><span data-stu-id="2f633-255">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="2f633-256">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="2f633-256">ICorDebugInternalFrame2</span></span>](icordebuginternalframe2-interface.md)|<span data-ttu-id="2f633-257">4</span><span class="sxs-lookup"><span data-stu-id="2f633-257">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="2f633-258">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="2f633-258">ICorDebugRuntimeUnwindableFrame</span></span>](icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="2f633-259">4</span><span class="sxs-lookup"><span data-stu-id="2f633-259">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="2f633-260">Интерфейс ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="2f633-260">ICorDebugHeapValue3 Interface</span></span>](icordebugheapvalue3-interface.md)|<span data-ttu-id="2f633-261">4</span><span class="sxs-lookup"><span data-stu-id="2f633-261">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="2f633-262">Интерфейс ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="2f633-262">ICorDebugBlockingObjectEnum Interface</span></span>](icordebugblockingobjectenum-interface.md)|<span data-ttu-id="2f633-263">4</span><span class="sxs-lookup"><span data-stu-id="2f633-263">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="2f633-264">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="2f633-264">ICorDebugValue3</span></span>](icordebugvalue3-interface.md)|<span data-ttu-id="2f633-265">4</span><span class="sxs-lookup"><span data-stu-id="2f633-265">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="2f633-266">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="2f633-266">ICorDebugComObjectValue</span></span>](icordebugcomobjectvalue-interface.md)|<span data-ttu-id="2f633-267">4,5</span><span class="sxs-lookup"><span data-stu-id="2f633-267">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="2f633-268">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="2f633-268">ICorDebugAppDomain3</span></span>](icordebugappdomain3-interface.md)|<span data-ttu-id="2f633-269">4,5</span><span class="sxs-lookup"><span data-stu-id="2f633-269">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="2f633-270">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="2f633-270">ICorDebugCode3</span></span>](icordebugcode3-interface.md)|<span data-ttu-id="2f633-271">4,5</span><span class="sxs-lookup"><span data-stu-id="2f633-271">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="2f633-272">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="2f633-272">ICorDebugILFrame3</span></span>](icordebugilframe3-interface.md)|<span data-ttu-id="2f633-273">4,5</span><span class="sxs-lookup"><span data-stu-id="2f633-273">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="2f633-274">Версия платформы .NET Framework (включая все пакеты обновления) — самая последняя.</span><span class="sxs-lookup"><span data-stu-id="2f633-274">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="2f633-275">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2f633-275">Remarks</span></span>  

 <span data-ttu-id="2f633-276">Отладчик может использовать `CorDebugInterfaceVersion` перечисление в функции [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) для указания самой высокой версии .NET Framework, поддерживаемой отладчиком.</span><span class="sxs-lookup"><span data-stu-id="2f633-276">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="2f633-277">Имена интерфейсов</span><span class="sxs-lookup"><span data-stu-id="2f633-277">Interface Names</span></span>  

 <span data-ttu-id="2f633-278">Число в конце каждого имени интерфейсов в API отладки (например, "3" в `ICorDebugThread3`) обозначает версию интерфейса, а не платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f633-278">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="2f633-279">Все имена интерфейсов в API отладки, кроме интерфейсов, появившихся в платформе .NET Framework версии 1, включают номера версий.</span><span class="sxs-lookup"><span data-stu-id="2f633-279">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="2f633-280">Любые совпадения между номерами версий интерфейсов и номерами версий платформы .NET Framework являются случайными.</span><span class="sxs-lookup"><span data-stu-id="2f633-280">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
- <span data-ttu-id="2f633-281">Интерфейсы, представленные в платформе .NET Framework версии 1.0, не включают цифры, потому что все они имеют версию 1.</span><span class="sxs-lookup"><span data-stu-id="2f633-281">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
- <span data-ttu-id="2f633-282">Платформа .NET Framework версии 1.1 использует интерфейсы версии 1.0 и не вводит никаких новых интерфейсов отладки.</span><span class="sxs-lookup"><span data-stu-id="2f633-282">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
- <span data-ttu-id="2f633-283">Четырнадцать интерфейсов отладки, представленных в платформе .NET Framework версии 2.0, являются логическими расширениями версии 1, а их названия содержат число "2".</span><span class="sxs-lookup"><span data-stu-id="2f633-283">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
- <span data-ttu-id="2f633-284">Платформы .NET Framework версий 3.0 и 3.5 используют существующие интерфейсы платформы .NET Framework версии 2.0 и не вводят никаких новых интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="2f633-284">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
- <span data-ttu-id="2f633-285">В .NET Framework 4 введены разные версии интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2f633-285">The .NET Framework 4 introduces a mix of interface versions.</span></span> <span data-ttu-id="2f633-286">Например, и `ICorDebugThread3`, и `ICorDebugThread4` отображаются как третья и четвертая версии интерфейса `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="2f633-286">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="2f633-287">В .NET Framework 4 также введена первая версия `ICorDebugStackWalk` интерфейса и вторая версия `ICorDebugNativeFrame` интерфейса ( `ICorDebugNativeFrame2` ).</span><span class="sxs-lookup"><span data-stu-id="2f633-287">The .NET Framework 4 also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f633-288">Требования</span><span class="sxs-lookup"><span data-stu-id="2f633-288">Requirements</span></span>  

 <span data-ttu-id="2f633-289">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f633-289">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f633-290">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f633-290">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f633-291">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f633-291">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f633-292">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f633-292">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f633-293">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2f633-293">See also</span></span>

- [<span data-ttu-id="2f633-294">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="2f633-294">Debugging Enumerations</span></span>](debugging-enumerations.md)
