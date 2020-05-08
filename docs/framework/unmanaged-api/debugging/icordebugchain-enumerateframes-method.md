---
title: Метод ICorDebugChain::EnumerateFrames
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: c8a62d8b4a4db0f36d991c32dbfc5bad68780f1b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894696"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="168fe-102">Метод ICorDebugChain::EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="168fe-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="168fe-103">Возвращает перечислитель, содержащий все управляемые кадры стека в цепочке, начиная с самого последнего кадра.</span><span class="sxs-lookup"><span data-stu-id="168fe-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="168fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="168fe-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="168fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="168fe-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="168fe-106">заполняет Указатель на адрес объекта ICorDebugFrameEnum, который является перечислителем для кадров стека.</span><span class="sxs-lookup"><span data-stu-id="168fe-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="168fe-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="168fe-107">Remarks</span></span>  
 <span data-ttu-id="168fe-108">Цепочка представляет физический стек вызовов для потока.</span><span class="sxs-lookup"><span data-stu-id="168fe-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="168fe-109">`EnumerateFrames` Метод должен вызываться только для управляемых цепочек.</span><span class="sxs-lookup"><span data-stu-id="168fe-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="168fe-110">API отладки не предоставляет методы для получения кадров, содержащихся в неуправляемых цепочках.</span><span class="sxs-lookup"><span data-stu-id="168fe-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="168fe-111">Для получения этих сведений отладчик должен использовать другие средства.</span><span class="sxs-lookup"><span data-stu-id="168fe-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="168fe-112">Требования</span><span class="sxs-lookup"><span data-stu-id="168fe-112">Requirements</span></span>  
 <span data-ttu-id="168fe-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="168fe-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="168fe-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="168fe-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="168fe-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="168fe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="168fe-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="168fe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
