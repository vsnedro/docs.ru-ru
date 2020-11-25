---
title: Метод ICorDebugThread::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
ms.openlocfilehash: 5debd09f3ca0b4562f62913f9530cc4fa6f9110b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728034"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="d773d-102">Метод ICorDebugThread::GetHandle</span><span class="sxs-lookup"><span data-stu-id="d773d-102">ICorDebugThread::GetHandle Method</span></span>

<span data-ttu-id="d773d-103">Возвращает текущий маркер для активной части этого ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="d773d-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d773d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d773d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d773d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d773d-105">Parameters</span></span>  

 `phThreadHandle`  
 <span data-ttu-id="d773d-106">заполняет Указатель на ХСРЕАД, который является маркером активной части этого потока.</span><span class="sxs-lookup"><span data-stu-id="d773d-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d773d-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d773d-107">Remarks</span></span>  

 <span data-ttu-id="d773d-108">Этот маркер может измениться при выполнении процесса и может отличаться для разных частей потока.</span><span class="sxs-lookup"><span data-stu-id="d773d-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="d773d-109">Этот обработчик принадлежит API отладки.</span><span class="sxs-lookup"><span data-stu-id="d773d-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="d773d-110">Отладчик должен дублировать его перед использованием.</span><span class="sxs-lookup"><span data-stu-id="d773d-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d773d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d773d-111">Requirements</span></span>  

 <span data-ttu-id="d773d-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d773d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d773d-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d773d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d773d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d773d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d773d-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d773d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
