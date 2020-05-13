---
title: Метод ICorDebugFunction2::GetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 56dc5f87b32b3aaa0bfbb69541d5a01ae26606ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213242"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="aa171-102">Метод ICorDebugFunction2::GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="aa171-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="aa171-103">Возвращает значение, указывающее, помечается ли функция, представленная этим объектом ICorDebugFunction2, как пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="aa171-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa171-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa171-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa171-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa171-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="aa171-106">заполняет Указатель на логическое значение, равное `true` , если эта функция помечена как пользовательский код; в противном случае — значение `false` .</span><span class="sxs-lookup"><span data-stu-id="aa171-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa171-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="aa171-107">Remarks</span></span>  
 <span data-ttu-id="aa171-108">Если функция, представленная этим объектом `ICorDebugFunction2` , не может быть отлажена, `pbIsJustMyCode` всегда будет иметь значение `false` .</span><span class="sxs-lookup"><span data-stu-id="aa171-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa171-109">Требования</span><span class="sxs-lookup"><span data-stu-id="aa171-109">Requirements</span></span>  
 <span data-ttu-id="aa171-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa171-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa171-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa171-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa171-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa171-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa171-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa171-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
