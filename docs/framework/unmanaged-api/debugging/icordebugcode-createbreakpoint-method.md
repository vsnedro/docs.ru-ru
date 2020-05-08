---
title: Метод ICorDebugCode::CreateBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
ms.openlocfilehash: 40582b1289875d5151ea96e3153c6e4760737e84
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893813"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="fc1a8-102">Метод ICorDebugCode::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fc1a8-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="fc1a8-103">Создает точку останова в этом сегменте кода в указанном смещении.</span><span class="sxs-lookup"><span data-stu-id="fc1a8-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc1a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc1a8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc1a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc1a8-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="fc1a8-106">окне Смещение для создания точки останова.</span><span class="sxs-lookup"><span data-stu-id="fc1a8-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="fc1a8-107">заполняет Указатель на адрес объекта "ICorDebugFunctionBreakpoint", представляющего точку останова.</span><span class="sxs-lookup"><span data-stu-id="fc1a8-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc1a8-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc1a8-108">Remarks</span></span>  
 <span data-ttu-id="fc1a8-109">Прежде чем точка останова станет активной, ее необходимо добавить в объект Process.</span><span class="sxs-lookup"><span data-stu-id="fc1a8-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="fc1a8-110">Если этот код является кодом на языке MSIL и имеется JIT-скомпилированная собственная версия кода, то точка останова будет применена и в JIT-скомпилированном коде.</span><span class="sxs-lookup"><span data-stu-id="fc1a8-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="fc1a8-111">(То же самое верно, если код компилируется позже.)</span><span class="sxs-lookup"><span data-stu-id="fc1a8-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc1a8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fc1a8-112">Requirements</span></span>  
 <span data-ttu-id="fc1a8-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc1a8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc1a8-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc1a8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc1a8-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc1a8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc1a8-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc1a8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
