---
title: Метод ICorDebugChainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
ms.openlocfilehash: 2d075820df534e08bdf4c2b75d36f6a60f979662
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894092"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="270e0-102">Метод ICorDebugChainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="270e0-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="270e0-103">Возвращает указанное число экземпляров ICorDebugChain из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="270e0-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="270e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="270e0-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="270e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="270e0-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="270e0-106">окне Число извлекаемых `ICorDebugChain` экземпляров.</span><span class="sxs-lookup"><span data-stu-id="270e0-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="270e0-107">заполняет Массив указателей, каждый из которых указывает на `ICorDebugChain` объект, представляющий цепочку.</span><span class="sxs-lookup"><span data-stu-id="270e0-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="270e0-108">заполняет Указатель на число фактически возвращенных `ICorDebugChain` экземпляров.</span><span class="sxs-lookup"><span data-stu-id="270e0-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="270e0-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="270e0-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="270e0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="270e0-110">Requirements</span></span>  
 <span data-ttu-id="270e0-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="270e0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="270e0-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="270e0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="270e0-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="270e0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="270e0-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="270e0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
