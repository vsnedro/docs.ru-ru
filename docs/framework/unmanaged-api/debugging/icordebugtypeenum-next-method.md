---
title: Метод ICorDebugTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
ms.openlocfilehash: 83adea3d659eea6d4af9ae364aad18df67e69c03
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396624"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="68f49-102">Метод ICorDebugTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="68f49-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="68f49-103">Возвращает количество экземпляров "ICorDebugType", заданных `celt` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="68f49-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68f49-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68f49-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68f49-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="68f49-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="68f49-106">окне Число `ICorDebugType` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="68f49-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="68f49-107">заполняет Массив указателей, каждый из которых указывает на `ICorDebugType` объект.</span><span class="sxs-lookup"><span data-stu-id="68f49-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="68f49-108">заполняет Указатель на число `ICorDebugType` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="68f49-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="68f49-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="68f49-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68f49-110">Требования</span><span class="sxs-lookup"><span data-stu-id="68f49-110">Requirements</span></span>  
 <span data-ttu-id="68f49-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68f49-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68f49-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68f49-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68f49-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68f49-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68f49-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68f49-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f49-115">См. также</span><span class="sxs-lookup"><span data-stu-id="68f49-115">See also</span></span>
