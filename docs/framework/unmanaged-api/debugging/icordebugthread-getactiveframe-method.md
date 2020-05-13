---
title: Метод ICorDebugThread::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: 843c6df1ef41fdd3227b92275182432ad4cc43b1
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379728"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="b3229-102">Метод ICorDebugThread::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="b3229-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="b3229-103">Возвращает указатель интерфейса на активный (самый последний) кадр для этого объекта ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="b3229-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3229-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3229-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3229-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3229-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="b3229-106">заполняет Указатель на адрес объекта интерфейса ICorDebugFrame, который представляет кадр.</span><span class="sxs-lookup"><span data-stu-id="b3229-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3229-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3229-107">Remarks</span></span>  
 <span data-ttu-id="b3229-108">`ppFrame`Если в настоящий момент нет активного кадра, параметр имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="b3229-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3229-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b3229-109">Requirements</span></span>  
 <span data-ttu-id="b3229-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3229-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3229-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3229-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3229-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3229-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3229-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3229-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
