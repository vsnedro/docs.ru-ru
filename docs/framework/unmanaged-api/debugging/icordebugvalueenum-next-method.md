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
ms.openlocfilehash: db1721fed6414310556ceac493275e069a781ac8
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397142"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="20524-102">Метод ICorDebugValueEnum::Next</span><span class="sxs-lookup"><span data-stu-id="20524-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="20524-103">Возвращает указанное число экземпляров "ICorDebugValue" из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="20524-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20524-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20524-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20524-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="20524-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="20524-106">окне Число `ICorDebugValue` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="20524-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="20524-107">заполняет Массив указателей, каждый из которых указывает на `ICorDebugValue` объект.</span><span class="sxs-lookup"><span data-stu-id="20524-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="20524-108">заполняет Указатель на число `ICorDebugValue` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="20524-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="20524-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="20524-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20524-110">Требования</span><span class="sxs-lookup"><span data-stu-id="20524-110">Requirements</span></span>  
 <span data-ttu-id="20524-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20524-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20524-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20524-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20524-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20524-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20524-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20524-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20524-115">См. также</span><span class="sxs-lookup"><span data-stu-id="20524-115">See also</span></span>
