---
title: Метод ICorDebugFrame::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
ms.openlocfilehash: 9f9a6238057f56459eb8dca2375da412c3cd569d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690321"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="05f44-102">Метод ICorDebugFrame::GetFunction</span><span class="sxs-lookup"><span data-stu-id="05f44-102">ICorDebugFrame::GetFunction Method</span></span>

<span data-ttu-id="05f44-103">Возвращает функцию, содержащую код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="05f44-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05f44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05f44-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05f44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="05f44-105">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="05f44-106">заполняет Указатель на адрес объекта ICorDebugFunction, представляющего функцию, содержащую код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="05f44-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05f44-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="05f44-107">Remarks</span></span>  

 <span data-ttu-id="05f44-108">`GetFunction`Метод может завершиться ошибкой, если фрейм не связан с какой-либо определенной функцией.</span><span class="sxs-lookup"><span data-stu-id="05f44-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05f44-109">Требования</span><span class="sxs-lookup"><span data-stu-id="05f44-109">Requirements</span></span>  

 <span data-ttu-id="05f44-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05f44-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05f44-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05f44-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05f44-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05f44-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05f44-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05f44-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
