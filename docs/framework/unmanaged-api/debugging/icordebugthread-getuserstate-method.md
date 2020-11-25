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
ms.openlocfilehash: dd3936656ce1c9482b7f07a5780fcf651356b4be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727969"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="f6037-102">Метод ICorDebugThread::GetUserState</span><span class="sxs-lookup"><span data-stu-id="f6037-102">ICorDebugThread::GetUserState Method</span></span>

<span data-ttu-id="f6037-103">Возвращает текущее пользовательское состояние этого ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="f6037-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6037-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6037-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6037-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6037-105">Parameters</span></span>  

 `pState`  
 <span data-ttu-id="f6037-106">заполняет Указатель на побитовую комбинацию значений перечисления Кордебугусерстате, описывающих текущее пользовательское состояние этого потока.</span><span class="sxs-lookup"><span data-stu-id="f6037-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6037-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f6037-107">Remarks</span></span>  

 <span data-ttu-id="f6037-108">Пользовательское состояние потока — это состояние потока, которое проверяется отлаживаемой программой.</span><span class="sxs-lookup"><span data-stu-id="f6037-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="f6037-109">Для потока может быть задано несколько битов состояния.</span><span class="sxs-lookup"><span data-stu-id="f6037-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6037-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f6037-110">Requirements</span></span>  

 <span data-ttu-id="f6037-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6037-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6037-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6037-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6037-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6037-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6037-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6037-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
