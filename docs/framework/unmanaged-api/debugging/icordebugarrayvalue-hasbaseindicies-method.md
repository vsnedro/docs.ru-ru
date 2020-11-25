---
title: Метод ICorDebugArrayValue::HasBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
ms.openlocfilehash: a9d1faf5a834cb5d9be19f995aaa3eee1202171b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727449"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="66f2f-102">Метод ICorDebugArrayValue::HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="66f2f-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>

<span data-ttu-id="66f2f-103">Возвращает значение, указывающее, имеют ли измерения данного массива базовый индекс, отличный от нуля.</span><span class="sxs-lookup"><span data-stu-id="66f2f-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66f2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66f2f-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66f2f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66f2f-105">Parameters</span></span>  

 `pbHasBaseIndicies`  
 <span data-ttu-id="66f2f-106">заполняет Указатель на логическое значение, равное, `true` Если одно или несколько измерений этого `ICorDebugArrayValue` объекта имеют базовый индекс ненулевого значения; в противном случае логическое значение равно `false` .</span><span class="sxs-lookup"><span data-stu-id="66f2f-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66f2f-107">Требования</span><span class="sxs-lookup"><span data-stu-id="66f2f-107">Requirements</span></span>  

 <span data-ttu-id="66f2f-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66f2f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66f2f-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66f2f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66f2f-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66f2f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66f2f-111">**.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66f2f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
