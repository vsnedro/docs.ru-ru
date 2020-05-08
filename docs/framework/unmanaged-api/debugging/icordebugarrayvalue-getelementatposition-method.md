---
title: Метод ICorDebugArrayValue::GetElementAtPosition
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
ms.openlocfilehash: 5644c20ec5df2606c7258131573691997f424e50
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895012"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="e232c-102">Метод ICorDebugArrayValue::GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="e232c-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="e232c-103">Возвращает элемент в заданной позиции, рассматривая массив как одномерный массив с отсчетом от нуля.</span><span class="sxs-lookup"><span data-stu-id="e232c-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e232c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e232c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e232c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e232c-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="e232c-106">окне Расположение извлекаемого элемента.</span><span class="sxs-lookup"><span data-stu-id="e232c-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e232c-107">заполняет Указатель на адрес объекта ICorDebugValue, который представляет значение элемента.</span><span class="sxs-lookup"><span data-stu-id="e232c-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e232c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="e232c-108">Remarks</span></span>  
 <span data-ttu-id="e232c-109">Компоновка многомерного массива соответствует стилю в C++ для макета массива.</span><span class="sxs-lookup"><span data-stu-id="e232c-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e232c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e232c-110">Requirements</span></span>  
 <span data-ttu-id="e232c-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e232c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e232c-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e232c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e232c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e232c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e232c-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e232c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
