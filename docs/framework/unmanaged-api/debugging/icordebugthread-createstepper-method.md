---
title: Метод ICorDebugThread::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: a74d32478bc88ee634fa5ff9b61ac2059bc8e302
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379720"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="7ad8d-102">Метод ICorDebugThread::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="7ad8d-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="7ad8d-103">Создает объект ICorDebugStepper, позволяющий выполнять пошаговую отладку активной рамки этого ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="7ad8d-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ad8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ad8d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ad8d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ad8d-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="7ad8d-106">заполняет Указатель на адрес `ICorDebugStepper` объекта, который допускает пошаговое выполнение активного кадра этого потока.</span><span class="sxs-lookup"><span data-stu-id="7ad8d-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ad8d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="7ad8d-107">Remarks</span></span>  
 <span data-ttu-id="7ad8d-108">Активным кадром может быть неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="7ad8d-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="7ad8d-109">`ICorDebugStepper`Для выполнения фактического пошагового шага необходимо использовать интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7ad8d-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ad8d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7ad8d-110">Requirements</span></span>  
 <span data-ttu-id="7ad8d-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ad8d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ad8d-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ad8d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ad8d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ad8d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ad8d-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ad8d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
