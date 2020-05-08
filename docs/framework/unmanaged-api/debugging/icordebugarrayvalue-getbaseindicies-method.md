---
title: Метод ICorDebugArrayValue::GetBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: 9aadbe7c6f18c6b15350267d1f9ecaa3a23cdd20
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895071"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="bd5e1-102">Метод ICorDebugArrayValue::GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="bd5e1-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="bd5e1-103">Возвращает базовый индекс каждого измерения в массиве.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd5e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd5e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd5e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd5e1-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="bd5e1-106">окне Число измерений данного `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="bd5e1-107">Это значение также является размером `indicies` массива, поскольку его размер равен числу измерений `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="bd5e1-108">заполняет Массив целых чисел, каждый из которых является базовым индексом (т. е. начальным индексом) измерения этого `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="bd5e1-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd5e1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bd5e1-109">Requirements</span></span>  
 <span data-ttu-id="bd5e1-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd5e1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd5e1-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd5e1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd5e1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd5e1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd5e1-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd5e1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
