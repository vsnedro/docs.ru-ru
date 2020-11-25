---
title: Метод ICorDebugValue3::GetSize64
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
ms.openlocfilehash: d1d057d38e16503175138c6ec978eb6c1f12bc6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722340"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="80506-102">Метод ICorDebugValue3::GetSize64</span><span class="sxs-lookup"><span data-stu-id="80506-102">ICorDebugValue3::GetSize64 Method</span></span>

<span data-ttu-id="80506-103">Возвращает размер данного объекта [ICorDebugValue3](icordebugvalue3-interface.md) в байтах.</span><span class="sxs-lookup"><span data-stu-id="80506-103">Gets the size, in bytes, of this [ICorDebugValue3](icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80506-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80506-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80506-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80506-105">Parameters</span></span>  

 <span data-ttu-id="80506-106">псизе</span><span class="sxs-lookup"><span data-stu-id="80506-106">pSize</span></span>  
 <span data-ttu-id="80506-107">заполняет Указатель на размер данного объекта в байтах.</span><span class="sxs-lookup"><span data-stu-id="80506-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80506-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="80506-108">Remarks</span></span>  

 <span data-ttu-id="80506-109">Если этот тип значения является ссылочным, этот метод возвращает размер указателя, а не размер объекта.</span><span class="sxs-lookup"><span data-stu-id="80506-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="80506-110">`ICorDebugValue3::GetSize`Метод отличается от метода [ICorDebugValue:: resize](icordebugvalue-getsize-method.md) в типе выходного параметра.</span><span class="sxs-lookup"><span data-stu-id="80506-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="80506-111">В [ICorDebugValue::-size](icordebugvalue-getsize-method.md)параметр Output имеет значение `ULONG32` ; в, а `ICorDebugValue3::GetSize` — `ULONG64` .</span><span class="sxs-lookup"><span data-stu-id="80506-111">In [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="80506-112">Это позволяет интерфейсу [ICorDebugValue3](icordebugvalue3-interface.md) сообщать размер массивов, ПРЕВЫШАЮЩИХ 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="80506-112">This enables the [ICorDebugValue3](icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80506-113">Требования</span><span class="sxs-lookup"><span data-stu-id="80506-113">Requirements</span></span>  

 <span data-ttu-id="80506-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80506-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80506-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80506-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80506-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80506-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80506-117">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80506-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80506-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="80506-118">See also</span></span>

- [<span data-ttu-id="80506-119">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="80506-119">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="80506-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="80506-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
