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
ms.openlocfilehash: 13125f60f596cb8a80d9c42c51a979f632de494b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379755"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="8e3ea-102">Метод ICorDebugThread::GetDebugState</span><span class="sxs-lookup"><span data-stu-id="8e3ea-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="8e3ea-103">Возвращает текущее состояние отладки этого объекта ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="8e3ea-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e3ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e3ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e3ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8e3ea-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="8e3ea-106">заполняет Указатель на побитовую комбинацию значений перечисления Кордебугсреадстате, описывающих текущее состояние отладки этого потока.</span><span class="sxs-lookup"><span data-stu-id="8e3ea-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e3ea-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e3ea-107">Remarks</span></span>  
 <span data-ttu-id="8e3ea-108">Если процесс в данный момент остановлен, `pState` представляет состояние отладки, которое существовало для этого потока, если процесс был продолжен, а не фактическое текущее состояние этого потока.</span><span class="sxs-lookup"><span data-stu-id="8e3ea-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e3ea-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8e3ea-109">Requirements</span></span>  
 <span data-ttu-id="8e3ea-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e3ea-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e3ea-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e3ea-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e3ea-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e3ea-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e3ea-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e3ea-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
