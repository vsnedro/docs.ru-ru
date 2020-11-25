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
ms.openlocfilehash: 20c8a1987e48a88a3b8c92cf9f36fb58166cda9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715985"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="6aeb5-102">Метод ICorDebugAppDomain::EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="6aeb5-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>

<span data-ttu-id="6aeb5-103">Возвращает перечислитель для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="6aeb5-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aeb5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6aeb5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aeb5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6aeb5-105">Parameters</span></span>  

 `ppBreakpoints`  
 <span data-ttu-id="6aeb5-106">заполняет Указатель на адрес объекта ICorDebugBreakpointEnum, который является перечислителем для всех активных точек останова в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="6aeb5-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6aeb5-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6aeb5-107">Remarks</span></span>  

 <span data-ttu-id="6aeb5-108">Перечислитель включает все типы точек останова, включая точки останова функции и точки останова в данных.</span><span class="sxs-lookup"><span data-stu-id="6aeb5-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aeb5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6aeb5-109">Requirements</span></span>  

 <span data-ttu-id="6aeb5-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6aeb5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aeb5-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6aeb5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6aeb5-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6aeb5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6aeb5-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aeb5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
