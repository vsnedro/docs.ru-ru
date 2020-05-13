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
ms.openlocfilehash: ed7110cb2e2b7a91ed81d2d81c2989d1733c1ee6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207315"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="2042c-102">Метод ICorDebugProcess::GetHandle</span><span class="sxs-lookup"><span data-stu-id="2042c-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="2042c-103">Возвращает маркер процесса.</span><span class="sxs-lookup"><span data-stu-id="2042c-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2042c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2042c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2042c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2042c-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="2042c-106">заполняет Указатель на `HPROCESS` , который является обработчиком для процесса.</span><span class="sxs-lookup"><span data-stu-id="2042c-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2042c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2042c-107">Remarks</span></span>  
 <span data-ttu-id="2042c-108">Полученный обработчик принадлежит интерфейсу отладки.</span><span class="sxs-lookup"><span data-stu-id="2042c-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="2042c-109">Отладчик должен дублировать этот обработчик перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="2042c-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2042c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2042c-110">Requirements</span></span>  
 <span data-ttu-id="2042c-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2042c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2042c-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2042c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2042c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2042c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2042c-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2042c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
