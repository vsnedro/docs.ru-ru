---
title: Метод ICorDebugValueEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
ms.openlocfilehash: e1c8d94a90092b1497267c78d5fadf5a6e6de707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684334"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="ecc21-102">Метод ICorDebugValueEnum::Next</span><span class="sxs-lookup"><span data-stu-id="ecc21-102">ICorDebugValueEnum::Next Method</span></span>

<span data-ttu-id="ecc21-103">Возвращает указанное число экземпляров "ICorDebugValue" из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="ecc21-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecc21-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecc21-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ecc21-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="ecc21-106">окне Число `ICorDebugValue` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ecc21-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="ecc21-107">заполняет Массив указателей, каждый из которых указывает на `ICorDebugValue` объект.</span><span class="sxs-lookup"><span data-stu-id="ecc21-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ecc21-108">заполняет Указатель на число `ICorDebugValue` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ecc21-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="ecc21-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="ecc21-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecc21-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ecc21-110">Requirements</span></span>  

 <span data-ttu-id="ecc21-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecc21-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecc21-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecc21-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecc21-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecc21-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecc21-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecc21-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc21-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ecc21-115">See also</span></span>
