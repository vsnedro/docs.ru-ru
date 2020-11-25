---
title: Метод ICorDebugFunction::CreateBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
ms.openlocfilehash: 2d1846acae51f416471404389dd1dbcfb2383760
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728177"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="6cd90-102">Метод ICorDebugFunction::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6cd90-102">ICorDebugFunction::CreateBreakpoint Method</span></span>

<span data-ttu-id="6cd90-103">Создает точку останова в начале этой функции.</span><span class="sxs-lookup"><span data-stu-id="6cd90-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cd90-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6cd90-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cd90-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6cd90-105">Parameters</span></span>  

 `ppBreakpoint`  
 <span data-ttu-id="6cd90-106">заполняет Указатель на адрес объекта ICorDebugFunctionBreakpoint, который представляет новую точку останова для функции.</span><span class="sxs-lookup"><span data-stu-id="6cd90-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cd90-107">Требования</span><span class="sxs-lookup"><span data-stu-id="6cd90-107">Requirements</span></span>  

 <span data-ttu-id="6cd90-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cd90-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cd90-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6cd90-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6cd90-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cd90-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cd90-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cd90-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
