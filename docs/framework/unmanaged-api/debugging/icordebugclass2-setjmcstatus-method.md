---
title: Метод ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: 9fb2f960098e970b4d3d9f0be499f4d9fda6558e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893895"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="f77c2-102">Метод ICorDebugClass2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="f77c2-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="f77c2-103">Для каждого метода класса задает значение, указывающее, является ли метод определяемым пользователем кодом.</span><span class="sxs-lookup"><span data-stu-id="f77c2-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f77c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f77c2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f77c2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f77c2-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="f77c2-106">окне Задайте значение `true` , чтобы указать, что метод является пользовательским кодом; в противном случае `false`задайте для значение.</span><span class="sxs-lookup"><span data-stu-id="f77c2-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f77c2-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f77c2-107">Remarks</span></span>  
 <span data-ttu-id="f77c2-108">Средство "только мой код" (JMC) пропускает код, не определенный пользователем.</span><span class="sxs-lookup"><span data-stu-id="f77c2-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="f77c2-109">Определяемый пользователем код должен быть подмножеством отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="f77c2-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="f77c2-110">`SetJMCStatus`Возвращает значение HRESULT, равное S_FALSE, если не удается задать значение для какого бы то ни было метода, даже если оно успешно задает значение для всех остальных методов.</span><span class="sxs-lookup"><span data-stu-id="f77c2-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f77c2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f77c2-111">Requirements</span></span>  
 <span data-ttu-id="f77c2-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f77c2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f77c2-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f77c2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f77c2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f77c2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f77c2-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f77c2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
