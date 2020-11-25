---
title: Метод ICorDebugThread::GetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
ms.openlocfilehash: 746fef3629e6573d7dfe47d5a3fcf9ee9a1d4250
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728047"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="faf54-102">Метод ICorDebugThread::GetDebugState</span><span class="sxs-lookup"><span data-stu-id="faf54-102">ICorDebugThread::GetDebugState Method</span></span>

<span data-ttu-id="faf54-103">Возвращает текущее состояние отладки этого объекта ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="faf54-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faf54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="faf54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faf54-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="faf54-105">Parameters</span></span>  

 `pState`  
 <span data-ttu-id="faf54-106">заполняет Указатель на побитовую комбинацию значений перечисления Кордебугсреадстате, описывающих текущее состояние отладки этого потока.</span><span class="sxs-lookup"><span data-stu-id="faf54-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faf54-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="faf54-107">Remarks</span></span>  

 <span data-ttu-id="faf54-108">Если процесс в данный момент остановлен, `pState` представляет состояние отладки, которое существовало для этого потока, если процесс был продолжен, а не фактическое текущее состояние этого потока.</span><span class="sxs-lookup"><span data-stu-id="faf54-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faf54-109">Требования</span><span class="sxs-lookup"><span data-stu-id="faf54-109">Requirements</span></span>  

 <span data-ttu-id="faf54-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faf54-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faf54-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faf54-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faf54-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faf54-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faf54-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faf54-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
