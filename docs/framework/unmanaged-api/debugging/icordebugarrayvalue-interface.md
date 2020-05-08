---
title: Интерфейс ICorDebugArrayValue
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
ms.openlocfilehash: bd1e86b83c43af20604416f158ab9e74f399821b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894971"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="bcd1a-102">Интерфейс ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="bcd1a-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="bcd1a-103">Подкласс ICorDebugHeapValue, представляющий одномерный или многомерный массив.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bcd1a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="bcd1a-104">Methods</span></span>  
  
|<span data-ttu-id="bcd1a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="bcd1a-105">Method</span></span>|<span data-ttu-id="bcd1a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="bcd1a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bcd1a-107">Метод GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="bcd1a-107">GetBaseIndicies Method</span></span>](icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="bcd1a-108">Возвращает базовый индекс каждого измерения в массиве.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="bcd1a-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="bcd1a-109">GetCount Method</span></span>](icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="bcd1a-110">Возвращает общее число элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="bcd1a-111">Метод GetDimensions</span><span class="sxs-lookup"><span data-stu-id="bcd1a-111">GetDimensions Method</span></span>](icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="bcd1a-112">Возвращает размеры массива.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="bcd1a-113">Метод GetElement</span><span class="sxs-lookup"><span data-stu-id="bcd1a-113">GetElement Method</span></span>](icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="bcd1a-114">Возвращает значение, представляющее заданный элемент в массиве.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="bcd1a-115">Метод GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="bcd1a-115">GetElementAtPosition Method</span></span>](icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="bcd1a-116">Возвращает элемент в заданной позиции, рассматривая массив как одномерный массив с отсчетом от нуля.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="bcd1a-117">Метод GetElementType</span><span class="sxs-lookup"><span data-stu-id="bcd1a-117">GetElementType Method</span></span>](icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="bcd1a-118">Возвращает простой тип элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="bcd1a-119">Метод GetRank</span><span class="sxs-lookup"><span data-stu-id="bcd1a-119">GetRank Method</span></span>](icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="bcd1a-120">Получает число измерений в массиве.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="bcd1a-121">Метод HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="bcd1a-121">HasBaseIndicies Method</span></span>](icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="bcd1a-122">Определяет, имеет ли массив базовые индексы.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcd1a-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="bcd1a-123">Remarks</span></span>  
 <span data-ttu-id="bcd1a-124">`ICorDebugArrayValue`поддерживает одномерный и многомерный массивы.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bcd1a-125">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="bcd1a-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcd1a-126">Требования</span><span class="sxs-lookup"><span data-stu-id="bcd1a-126">Requirements</span></span>  
 <span data-ttu-id="bcd1a-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcd1a-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcd1a-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcd1a-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcd1a-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcd1a-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcd1a-130">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcd1a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd1a-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bcd1a-131">See also</span></span>

- [<span data-ttu-id="bcd1a-132">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bcd1a-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
