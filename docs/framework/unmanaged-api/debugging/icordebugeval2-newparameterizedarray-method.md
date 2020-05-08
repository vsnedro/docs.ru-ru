---
title: Метод ICorDebugEval2::NewParameterizedArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
ms.openlocfilehash: 9d589bfc3093d03d87acb47ade0fc6c972bcd335
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976113"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="1f79c-102">Метод ICorDebugEval2::NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="1f79c-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="1f79c-103">Выделяет новый массив указанного типа элемента и измерений.</span><span class="sxs-lookup"><span data-stu-id="1f79c-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f79c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f79c-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f79c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f79c-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="1f79c-106">окне Указатель на объект ICorDebugType, представляющий тип элемента, хранящегося в массиве.</span><span class="sxs-lookup"><span data-stu-id="1f79c-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="1f79c-107">окне Число измерений массива.</span><span class="sxs-lookup"><span data-stu-id="1f79c-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="1f79c-108">В .NET Framework версии 2,0 это значение должно быть равно 1.</span><span class="sxs-lookup"><span data-stu-id="1f79c-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="1f79c-109">окне Размер каждого измерения массива в байтах.</span><span class="sxs-lookup"><span data-stu-id="1f79c-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="1f79c-110">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="1f79c-110">[in] Optional.</span></span> <span data-ttu-id="1f79c-111">Нижняя граница каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="1f79c-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="1f79c-112">Если это значение пропущено, для каждого измерения предполагается Нижняя граница, равная нулю.</span><span class="sxs-lookup"><span data-stu-id="1f79c-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f79c-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f79c-113">Remarks</span></span>  
 <span data-ttu-id="1f79c-114">Элементы массива могут быть экземплярами универсального типа.</span><span class="sxs-lookup"><span data-stu-id="1f79c-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="1f79c-115">Массив всегда создается в домене приложения, в котором в данный момент выполняется поток.</span><span class="sxs-lookup"><span data-stu-id="1f79c-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="1f79c-116">В .NET Framework 2,0 значение `rank` должно быть равно 1.</span><span class="sxs-lookup"><span data-stu-id="1f79c-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f79c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="1f79c-117">Requirements</span></span>  
 <span data-ttu-id="1f79c-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f79c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f79c-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f79c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f79c-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f79c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f79c-121">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f79c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
