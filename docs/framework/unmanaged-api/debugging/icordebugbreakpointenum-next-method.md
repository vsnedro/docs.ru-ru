---
title: Метод ICorDebugBreakpointEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
ms.openlocfilehash: af90886390b59932d3ae146a70fc2901ec1c378d
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894671"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="8efe7-102">Метод ICorDebugBreakpointEnum::Next</span><span class="sxs-lookup"><span data-stu-id="8efe7-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="8efe7-103">Возвращает указанное число экземпляров Икордебугбреакпоинт из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="8efe7-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8efe7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8efe7-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8efe7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8efe7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8efe7-106">окне Число извлекаемых `ICorDebugBreakpoint` экземпляров.</span><span class="sxs-lookup"><span data-stu-id="8efe7-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="8efe7-107">заполняет Массив указателей, каждый из которых указывает на `ICorDebugBreakpoint` объект, представляющий точку останова.</span><span class="sxs-lookup"><span data-stu-id="8efe7-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8efe7-108">заполняет Указатель на число фактически возвращенных `ICorDebugBreakpoint` экземпляров.</span><span class="sxs-lookup"><span data-stu-id="8efe7-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="8efe7-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="8efe7-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8efe7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8efe7-110">Requirements</span></span>  
 <span data-ttu-id="8efe7-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8efe7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8efe7-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8efe7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8efe7-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8efe7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8efe7-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8efe7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
