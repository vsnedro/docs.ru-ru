---
title: Метод ICorDebugFunctionBreakpoint::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type:
- apiref
ms.openlocfilehash: 4ef5728e4b13d6d3d73aef06f9f7f50ab22609ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726266"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="2e9f0-102">Метод ICorDebugFunctionBreakpoint::GetFunction</span><span class="sxs-lookup"><span data-stu-id="2e9f0-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>

<span data-ttu-id="2e9f0-103">Возвращает указатель на интерфейс ICorDebugFunction, ссылающийся на функцию, в которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="2e9f0-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e9f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e9f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e9f0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e9f0-105">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="2e9f0-106">заполняет Указатель на адрес функции, в которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="2e9f0-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e9f0-107">Требования</span><span class="sxs-lookup"><span data-stu-id="2e9f0-107">Requirements</span></span>  

 <span data-ttu-id="2e9f0-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e9f0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e9f0-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e9f0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e9f0-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e9f0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e9f0-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e9f0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
