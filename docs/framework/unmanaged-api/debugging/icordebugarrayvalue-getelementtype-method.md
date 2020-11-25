---
title: Метод ICorDebugArrayValue::GetElementType
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
ms.openlocfilehash: 1deadef7517772460adc96cd0dd630d85cb21c9f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698173"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="a9fbc-102">Метод ICorDebugArrayValue::GetElementType</span><span class="sxs-lookup"><span data-stu-id="a9fbc-102">ICorDebugArrayValue::GetElementType Method</span></span>

<span data-ttu-id="a9fbc-103">Возвращает значение, указывающее простой тип элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="a9fbc-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9fbc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9fbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9fbc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9fbc-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="a9fbc-106">заполняет Указатель на значение перечисления Корелементтипе, указывающее тип.</span><span class="sxs-lookup"><span data-stu-id="a9fbc-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9fbc-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a9fbc-107">Requirements</span></span>  

 <span data-ttu-id="a9fbc-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9fbc-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9fbc-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9fbc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9fbc-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9fbc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9fbc-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9fbc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
