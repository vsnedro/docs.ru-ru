---
title: Метод ICorDebugController::IsRunning
ms.date: 03/30/2017
api_name:
- ICorDebugController.IsRunning
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type:
- apiref
ms.openlocfilehash: 73ed86ee12b02d292dc6dfc1d652459a679f81ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679942"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="a242a-102">Метод ICorDebugController::IsRunning</span><span class="sxs-lookup"><span data-stu-id="a242a-102">ICorDebugController::IsRunning Method</span></span>

<span data-ttu-id="a242a-103">Возвращает значение, указывающее, выполняются ли в настоящий момент потоки в процессе.</span><span class="sxs-lookup"><span data-stu-id="a242a-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a242a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a242a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a242a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a242a-105">Parameters</span></span>  

 `pbRunning`  
 <span data-ttu-id="a242a-106">заполняет Указатель на значение, равное, `true` Если потоки в процессе выполняются свободно; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="a242a-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a242a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a242a-107">Requirements</span></span>  

 <span data-ttu-id="a242a-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a242a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a242a-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a242a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a242a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a242a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a242a-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a242a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a242a-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a242a-112">See also</span></span>
