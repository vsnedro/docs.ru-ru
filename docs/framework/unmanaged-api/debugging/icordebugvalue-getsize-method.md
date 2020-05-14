---
title: Метод ICorDebugValue::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 9ff7128f55236ae4d0c3a9067a279c496cfb6798
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396753"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="1c123-102">Метод ICorDebugValue::GetSize</span><span class="sxs-lookup"><span data-stu-id="1c123-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="1c123-103">Возвращает размер этого объекта "ICorDebugValue" в байтах.</span><span class="sxs-lookup"><span data-stu-id="1c123-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c123-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c123-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c123-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c123-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="1c123-106">заполняет Размер данного объекта значения в байтах.</span><span class="sxs-lookup"><span data-stu-id="1c123-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c123-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c123-107">Remarks</span></span>  
 <span data-ttu-id="1c123-108">Если типом значения является ссылочный тип, этот метод возвращает размер указателя, а не размер объекта.</span><span class="sxs-lookup"><span data-stu-id="1c123-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="1c123-109">`ICorDebugValue::GetSize`Метод возвращает `COR_E_OVERFLOW` для объектов, размер которых ПРЕВЫШАЕТ 4 гб на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="1c123-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="1c123-110">Используйте вместо него метод [ICorDebugValue3:: GetSize64](icordebugvalue3-getsize64-method.md) для объектов, размер которых ПРЕВЫШАЕТ 4 ГБ.</span><span class="sxs-lookup"><span data-stu-id="1c123-110">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c123-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1c123-111">Requirements</span></span>  
 <span data-ttu-id="1c123-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c123-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c123-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c123-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c123-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c123-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c123-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c123-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c123-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="1c123-116">See also</span></span>

- [<span data-ttu-id="1c123-117">Метод GetSize64</span><span class="sxs-lookup"><span data-stu-id="1c123-117">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
