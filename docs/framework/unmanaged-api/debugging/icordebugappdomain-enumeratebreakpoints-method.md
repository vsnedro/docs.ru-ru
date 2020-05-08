---
title: Метод ICorDebugAppDomain::EnumerateBreakpoints
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
ms.openlocfilehash: bb994ae32c9e0e61c06c60521361a5c6c78d12fa
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895278"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="0f2df-102">Метод ICorDebugAppDomain::EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="0f2df-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="0f2df-103">Возвращает перечислитель для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="0f2df-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f2df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f2df-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f2df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f2df-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="0f2df-106">заполняет Указатель на адрес объекта ICorDebugBreakpointEnum, который является перечислителем для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="0f2df-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f2df-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f2df-107">Remarks</span></span>  
 <span data-ttu-id="0f2df-108">Перечислитель включает все типы точек останова, включая точки останова функции и точки останова в данных.</span><span class="sxs-lookup"><span data-stu-id="0f2df-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f2df-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0f2df-109">Requirements</span></span>  
 <span data-ttu-id="0f2df-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f2df-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f2df-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f2df-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f2df-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f2df-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f2df-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f2df-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
