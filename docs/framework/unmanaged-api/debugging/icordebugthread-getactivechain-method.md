---
title: Метод ICorDebugThread::GetActiveChain
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
ms.openlocfilehash: e6b1d78b2bd95ea27f4b19a045cd2680342e8a80
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728099"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="6f8b1-102">Метод ICorDebugThread::GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="6f8b1-102">ICorDebugThread::GetActiveChain Method</span></span>

<span data-ttu-id="6f8b1-103">Возвращает указатель интерфейса на активную (последнюю) цепь стека на этом объекте ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="6f8b1-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f8b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f8b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f8b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f8b1-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="6f8b1-106">заполняет Указатель на адрес объекта ICorDebugChain, который представляет цепочку стека.</span><span class="sxs-lookup"><span data-stu-id="6f8b1-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f8b1-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6f8b1-107">Remarks</span></span>  

 <span data-ttu-id="6f8b1-108">`ppChain`Параметр имеет значение null, если цепочка стека в данный момент не активна.</span><span class="sxs-lookup"><span data-stu-id="6f8b1-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f8b1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6f8b1-109">Requirements</span></span>  

 <span data-ttu-id="6f8b1-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f8b1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f8b1-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f8b1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f8b1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f8b1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f8b1-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f8b1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
