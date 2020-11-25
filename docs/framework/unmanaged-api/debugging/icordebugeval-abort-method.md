---
title: Метод ICorDebugEval::Abort
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: 6e6ea5e42c5e1b1943a080ae02e1dbf6d702bebc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705856"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="013f8-102">Метод ICorDebugEval::Abort</span><span class="sxs-lookup"><span data-stu-id="013f8-102">ICorDebugEval::Abort Method</span></span>

<span data-ttu-id="013f8-103">Прерывает вычисление, которое данный объект ICorDebugEval сейчас выполняет.</span><span class="sxs-lookup"><span data-stu-id="013f8-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="013f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="013f8-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="013f8-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="013f8-105">Remarks</span></span>  

 <span data-ttu-id="013f8-106">Если оценка является вложенной и не является самой последней, `Abort` метод может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="013f8-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="013f8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="013f8-107">Requirements</span></span>  

 <span data-ttu-id="013f8-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="013f8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="013f8-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="013f8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="013f8-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="013f8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="013f8-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="013f8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
