---
title: Метод ICorDebugBreakpoint::Activate
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
ms.openlocfilehash: 70a07f0ce7f1fa4c904fde594dcf82c5149616fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721534"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="bdc02-102">Метод ICorDebugBreakpoint::Activate</span><span class="sxs-lookup"><span data-stu-id="bdc02-102">ICorDebugBreakpoint::Activate Method</span></span>

<span data-ttu-id="bdc02-103">Задает активное состояние этого объекта `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="bdc02-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdc02-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdc02-104">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdc02-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdc02-105">Parameters</span></span>  

 `bActive`  
 <span data-ttu-id="bdc02-106">окне Установите это значение, чтобы `true` указать состояние как активное; в противном случае задайте для этого параметра значение `false` .</span><span class="sxs-lookup"><span data-stu-id="bdc02-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdc02-107">Требования</span><span class="sxs-lookup"><span data-stu-id="bdc02-107">Requirements</span></span>  

 <span data-ttu-id="bdc02-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdc02-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdc02-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdc02-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdc02-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdc02-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdc02-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdc02-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
