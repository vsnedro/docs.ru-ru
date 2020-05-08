---
title: Метод ICorDebugCode::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
ms.openlocfilehash: 9f785eafa8925324e3bd269ca08a3b1367b74c44
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893591"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="9738a-102">Метод ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="9738a-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="9738a-103">Возвращает "ICorDebugFunction", связанный с этим "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="9738a-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9738a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9738a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9738a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9738a-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="9738a-106">заполняет Указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="9738a-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9738a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9738a-107">Remarks</span></span>  
 <span data-ttu-id="9738a-108">`ICorDebugCode`и `ICorDebugFunction` поддерживают связь «один к одному».</span><span class="sxs-lookup"><span data-stu-id="9738a-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9738a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9738a-109">Requirements</span></span>  
 <span data-ttu-id="9738a-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9738a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9738a-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9738a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9738a-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9738a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9738a-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9738a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
