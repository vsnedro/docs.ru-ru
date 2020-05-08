---
title: Метод ICorDebugChain::GetNext
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetNext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type:
- apiref
ms.openlocfilehash: 47a90ed63ae217cb150f392ad9196f8d0d5764e3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894644"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="46e19-102">Метод ICorDebugChain::GetNext</span><span class="sxs-lookup"><span data-stu-id="46e19-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="46e19-103">Возвращает следующую цепь кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="46e19-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e19-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46e19-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46e19-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46e19-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="46e19-106">заполняет Указатель на адрес объекта ICorDebugChain, который представляет следующую цепь кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="46e19-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="46e19-107">Если цепочка является последней, `ppChain` значение равно null.</span><span class="sxs-lookup"><span data-stu-id="46e19-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46e19-108">Требования</span><span class="sxs-lookup"><span data-stu-id="46e19-108">Requirements</span></span>  
 <span data-ttu-id="46e19-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46e19-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46e19-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46e19-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46e19-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46e19-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46e19-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46e19-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
