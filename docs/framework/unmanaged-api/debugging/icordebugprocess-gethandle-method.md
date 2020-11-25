---
title: Метод ICorDebugProcess::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: 87b7b7381ef53f7e2abebc053b5c9f87f94d96c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695079"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="8dca4-102">Метод ICorDebugProcess::GetHandle</span><span class="sxs-lookup"><span data-stu-id="8dca4-102">ICorDebugProcess::GetHandle Method</span></span>

<span data-ttu-id="8dca4-103">Возвращает маркер процесса.</span><span class="sxs-lookup"><span data-stu-id="8dca4-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dca4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8dca4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dca4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8dca4-105">Parameters</span></span>  

 `phProcessHandle`  
 <span data-ttu-id="8dca4-106">заполняет Указатель на `HPROCESS` , который является обработчиком для процесса.</span><span class="sxs-lookup"><span data-stu-id="8dca4-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dca4-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8dca4-107">Remarks</span></span>  

 <span data-ttu-id="8dca4-108">Полученный обработчик принадлежит интерфейсу отладки.</span><span class="sxs-lookup"><span data-stu-id="8dca4-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="8dca4-109">Отладчик должен дублировать этот обработчик перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="8dca4-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dca4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8dca4-110">Requirements</span></span>  

 <span data-ttu-id="8dca4-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dca4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dca4-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8dca4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8dca4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dca4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8dca4-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dca4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
