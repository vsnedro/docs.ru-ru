---
title: Метод ICorDebugArrayValue::GetElement
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
ms.openlocfilehash: 7a52e61f41bd1d7f68523dd16f70010ffbba401e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895025"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="35fa4-102">Метод ICorDebugArrayValue::GetElement</span><span class="sxs-lookup"><span data-stu-id="35fa4-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="35fa4-103">Возвращает значение заданного элемента массива.</span><span class="sxs-lookup"><span data-stu-id="35fa4-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35fa4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35fa4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35fa4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="35fa4-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="35fa4-106">окне Число измерений данного `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="35fa4-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="35fa4-107">Это значение также является размером `indices` массива, поскольку его размер равен числу измерений `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="35fa4-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="35fa4-108">окне Массив значений индекса, каждый из которых задает позиции в измерении `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="35fa4-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="35fa4-109">Это значение не должно быть равно null.</span><span class="sxs-lookup"><span data-stu-id="35fa4-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="35fa4-110">заполняет Указатель на адрес объекта ICorDebugValue, представляющий значение указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="35fa4-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35fa4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="35fa4-111">Requirements</span></span>  
 <span data-ttu-id="35fa4-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35fa4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35fa4-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35fa4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35fa4-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35fa4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35fa4-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35fa4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
