---
title: Метод ICorDebugEval::IsActive
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
ms.openlocfilehash: 5ac221b0b5837175b8073ab29f94c1f28078d3e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729776"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="7a2a2-102">Метод ICorDebugEval::IsActive</span><span class="sxs-lookup"><span data-stu-id="7a2a2-102">ICorDebugEval::IsActive Method</span></span>

<span data-ttu-id="7a2a2-103">Возвращает значение, указывающее, выполняется ли в данный момент объект ICorDebugEval.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a2a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a2a2-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a2a2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7a2a2-105">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="7a2a2-106">заполняет Указатель на значение, указывающее, активна ли эта оценка.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a2a2-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7a2a2-107">Requirements</span></span>  

 <span data-ttu-id="7a2a2-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a2a2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a2a2-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a2a2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a2a2-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a2a2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a2a2-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a2a2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
