---
title: Метод ICorDebugThread::GetUserState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
ms.openlocfilehash: d1ff3427feb5dc8395bbb2fda78e3e93e1a1a8f0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378848"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="5f6f0-102">Метод ICorDebugThread::GetUserState</span><span class="sxs-lookup"><span data-stu-id="5f6f0-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="5f6f0-103">Возвращает текущее пользовательское состояние этого ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f6f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f6f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f6f0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f6f0-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="5f6f0-106">заполняет Указатель на побитовую комбинацию значений перечисления Кордебугусерстате, описывающих текущее пользовательское состояние этого потока.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f6f0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5f6f0-107">Remarks</span></span>  
 <span data-ttu-id="5f6f0-108">Пользовательское состояние потока — это состояние потока, которое проверяется отлаживаемой программой.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="5f6f0-109">Для потока может быть задано несколько битов состояния.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f6f0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5f6f0-110">Requirements</span></span>  
 <span data-ttu-id="5f6f0-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f6f0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f6f0-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f6f0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f6f0-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f6f0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f6f0-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f6f0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
