---
title: Метод ICorDebugChain::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
ms.openlocfilehash: a6d26924773e6ad505975402ec3ace150d02cc3a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894616"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="a03ad-102">Метод ICorDebugChain::GetCaller</span><span class="sxs-lookup"><span data-stu-id="a03ad-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="a03ad-103">Возвращает цепочку, вызвавшую эту цепь.</span><span class="sxs-lookup"><span data-stu-id="a03ad-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a03ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a03ad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a03ad-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a03ad-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="a03ad-106">заполняет Указатель на адрес объекта ICorDebugChain, который представляет вызывающую цепочку.</span><span class="sxs-lookup"><span data-stu-id="a03ad-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="a03ad-107">Если эта цепочка была вызвана недостаточной (как в случае, если эта цепочка или отладчик инициализируют стек вызовов), `ppChain` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="a03ad-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a03ad-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a03ad-108">Remarks</span></span>  
 <span data-ttu-id="a03ad-109">Вызывающая цепочка может находиться в другом потоке, если вызов был маршалирован в потоках.</span><span class="sxs-lookup"><span data-stu-id="a03ad-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a03ad-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a03ad-110">Requirements</span></span>  
 <span data-ttu-id="a03ad-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a03ad-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a03ad-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a03ad-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a03ad-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a03ad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a03ad-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a03ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
