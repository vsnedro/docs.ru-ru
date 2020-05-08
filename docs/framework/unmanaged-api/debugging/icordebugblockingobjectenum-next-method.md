---
title: Метод ICorDebugBlockingObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
ms.openlocfilehash: 0ef49d2d833841eac62b2b964a0fdc902b4fb6a9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894770"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="490d3-102">Метод ICorDebugBlockingObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="490d3-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="490d3-103">Возвращает указанное число объектов [CorDebugBlockingObject](cordebugblockingobject-structure.md) из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="490d3-103">Gets the specified number of [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="490d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="490d3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="490d3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="490d3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="490d3-106">окне Число извлекаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="490d3-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="490d3-107">заполняет Массив указателей на объекты [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="490d3-107">[out] An array of pointers to [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="490d3-108">заполняет Указатель на количество полученных объектов.</span><span class="sxs-lookup"><span data-stu-id="490d3-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="490d3-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="490d3-109">Return Value</span></span>  
 <span data-ttu-id="490d3-110">Этот метод возвращает следующие специфичные результаты HRESULT.</span><span class="sxs-lookup"><span data-stu-id="490d3-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="490d3-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="490d3-111">HRESULT</span></span>|<span data-ttu-id="490d3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="490d3-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="490d3-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="490d3-113">S_OK</span></span>|<span data-ttu-id="490d3-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="490d3-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="490d3-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="490d3-115">S_FALSE</span></span>|<span data-ttu-id="490d3-116">Значение параметра `pceltFetched` не равно `celt`.</span><span class="sxs-lookup"><span data-stu-id="490d3-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="490d3-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="490d3-117">Remarks</span></span>  
 <span data-ttu-id="490d3-118">Этот метод работает, как типичный перечислитель COM.</span><span class="sxs-lookup"><span data-stu-id="490d3-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="490d3-119">Значения входного массива должны иметь размер `celt`не ниже.</span><span class="sxs-lookup"><span data-stu-id="490d3-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="490d3-120">Массив будет заполнен либо следующими `celt` значениями в перечислении, либо со всеми оставшимися значениями, если они меньше, `celt` чем осталось.</span><span class="sxs-lookup"><span data-stu-id="490d3-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="490d3-121">При возврате из этого `pceltFetched` метода будет заполнено количество полученных значений.</span><span class="sxs-lookup"><span data-stu-id="490d3-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="490d3-122">Если `values` содержит недопустимые указатели или указывает на буфер, который `celt`меньше, или `pceltFetched` если является недопустимым указателем, результат не определен.</span><span class="sxs-lookup"><span data-stu-id="490d3-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="490d3-123">Хотя структуру [CorDebugBlockingObject](cordebugblockingobject-structure.md) не нужно освобождать, интерфейс "ICorDebugValue" внутри него должен быть освобожден.</span><span class="sxs-lookup"><span data-stu-id="490d3-123">Although the [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="490d3-124">Требования</span><span class="sxs-lookup"><span data-stu-id="490d3-124">Requirements</span></span>  
 <span data-ttu-id="490d3-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="490d3-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="490d3-126">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="490d3-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="490d3-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="490d3-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="490d3-128">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="490d3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="490d3-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="490d3-129">See also</span></span>

- [<span data-ttu-id="490d3-130">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="490d3-130">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="490d3-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="490d3-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="490d3-132">Отладка</span><span class="sxs-lookup"><span data-stu-id="490d3-132">Debugging</span></span>](index.md)
