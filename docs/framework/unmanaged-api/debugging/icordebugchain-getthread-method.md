---
title: Метод ICorDebugChain::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
ms.openlocfilehash: ad220289b45078130a0a41e67373fd3384ae9682
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724420"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="a552b-102">Метод ICorDebugChain::GetThread</span><span class="sxs-lookup"><span data-stu-id="a552b-102">ICorDebugChain::GetThread Method</span></span>

<span data-ttu-id="a552b-103">Возвращает физический поток, частью которого является эта цепочка вызовов.</span><span class="sxs-lookup"><span data-stu-id="a552b-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a552b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a552b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a552b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a552b-105">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="a552b-106">заполняет Указатель на объект ICorDebugThread, представляющий физический поток, частью которого является эта цепочка вызовов.</span><span class="sxs-lookup"><span data-stu-id="a552b-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a552b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a552b-107">Requirements</span></span>  

 <span data-ttu-id="a552b-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a552b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a552b-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a552b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a552b-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a552b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a552b-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a552b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
