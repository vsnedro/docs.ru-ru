---
title: Метод ICorDebugFunction2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
ms.openlocfilehash: 7da12554ba1db9a467aa03c01bfb3b584125b129
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213196"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="ea8a4-102">Метод ICorDebugFunction2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="ea8a4-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="ea8a4-103">Помечает функцию, представленную этим ICorDebugFunction2, для Только мой код пошагового выполнения.</span><span class="sxs-lookup"><span data-stu-id="ea8a4-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea8a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea8a4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea8a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea8a4-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="ea8a4-106">окне Установите значение, чтобы `true` пометить функцию как пользовательский код; в противном случае задайте для значение `false` .</span><span class="sxs-lookup"><span data-stu-id="ea8a4-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="ea8a4-107">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="ea8a4-107">Return Values</span></span>  
  
|<span data-ttu-id="ea8a4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea8a4-108">HRESULT</span></span>|<span data-ttu-id="ea8a4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ea8a4-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ea8a4-110">Функция была успешно помечена.</span><span class="sxs-lookup"><span data-stu-id="ea8a4-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="ea8a4-111">Функция не может быть помечена как пользовательский код, так как ее отладка невозможна.</span><span class="sxs-lookup"><span data-stu-id="ea8a4-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea8a4-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="ea8a4-112">Remarks</span></span>  
 <span data-ttu-id="ea8a4-113">Только мой код пошаговое средство пропускает код, не являющийся пользовательским.</span><span class="sxs-lookup"><span data-stu-id="ea8a4-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="ea8a4-114">Пользовательский код должен быть подмножеством отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="ea8a4-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea8a4-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ea8a4-115">Requirements</span></span>  
 <span data-ttu-id="ea8a4-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea8a4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea8a4-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea8a4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea8a4-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea8a4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea8a4-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea8a4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
