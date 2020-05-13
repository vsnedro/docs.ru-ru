---
title: Метод ICorDebugThread::CreateEval
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
ms.openlocfilehash: f66ef88646c314502dcb610cec8ce822cab1fca2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379284"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="a9eac-102">Метод ICorDebugThread::CreateEval</span><span class="sxs-lookup"><span data-stu-id="a9eac-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="a9eac-103">Создает объект ICorDebugEval, который собирает и предоставляет функциональные возможности этого ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="a9eac-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9eac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9eac-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9eac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9eac-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="a9eac-106">заполняет Указатель на адрес `ICorDebugEval` объекта, который собирает и предоставляет функциональные возможности этого потока.</span><span class="sxs-lookup"><span data-stu-id="a9eac-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9eac-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a9eac-107">Remarks</span></span>  
 <span data-ttu-id="a9eac-108">Объект вычисления перед выполнением вычислений выдаст новую цепочку в потоке.</span><span class="sxs-lookup"><span data-stu-id="a9eac-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="a9eac-109">Это прерывает вычисления, выполняемые в данный момент в потоке до завершения оценки.</span><span class="sxs-lookup"><span data-stu-id="a9eac-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9eac-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a9eac-110">Requirements</span></span>  
 <span data-ttu-id="a9eac-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9eac-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9eac-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9eac-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9eac-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9eac-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9eac-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9eac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
