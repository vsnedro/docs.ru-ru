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
ms.openlocfilehash: 0f42020821ec71d1e59ae8097f22ee530e16a576
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706181"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="4135a-102">Метод ICorDebugChainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="4135a-102">ICorDebugChainEnum::Next Method</span></span>

<span data-ttu-id="4135a-103">Возвращает указанное число экземпляров ICorDebugChain из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="4135a-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4135a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4135a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4135a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4135a-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="4135a-106">окне Число `ICorDebugChain` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4135a-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="4135a-107">заполняет Массив указателей, каждый из которых указывает на `ICorDebugChain` объект, представляющий цепочку.</span><span class="sxs-lookup"><span data-stu-id="4135a-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4135a-108">заполняет Указатель на число `ICorDebugChain` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="4135a-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="4135a-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="4135a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4135a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4135a-110">Requirements</span></span>  

 <span data-ttu-id="4135a-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4135a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4135a-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4135a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4135a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4135a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4135a-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4135a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
