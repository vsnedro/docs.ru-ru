---
title: Метод ICorDebugArrayValue::GetDimensions
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: fa2be894af6e44d09c25a736f45acba56052f9fa
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895042"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="52115-102">Метод ICorDebugArrayValue::GetDimensions</span><span class="sxs-lookup"><span data-stu-id="52115-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="52115-103">Возвращает количество элементов в каждом измерении этого массива.</span><span class="sxs-lookup"><span data-stu-id="52115-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52115-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52115-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52115-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52115-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="52115-106">окне Число измерений данного объекта ICorDebugArrayValue.</span><span class="sxs-lookup"><span data-stu-id="52115-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="52115-107">Это значение также является размером `dims` массива, поскольку его размер равен числу измерений `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="52115-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="52115-108">заполняет Массив целых чисел, каждый из которых указывает количество элементов в измерении в этом `ICorDebugArrayValue` объекте.</span><span class="sxs-lookup"><span data-stu-id="52115-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52115-109">Требования</span><span class="sxs-lookup"><span data-stu-id="52115-109">Requirements</span></span>  
 <span data-ttu-id="52115-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52115-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52115-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52115-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52115-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52115-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52115-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52115-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
