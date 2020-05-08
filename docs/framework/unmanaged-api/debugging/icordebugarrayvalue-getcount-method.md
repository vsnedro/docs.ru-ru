---
title: Метод ICorDebugArrayValue::GetCount
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
ms.openlocfilehash: 82f282630a2e31b8c67d43fa0f0b30431a0d6ee4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895057"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="02db7-102">Метод ICorDebugArrayValue::GetCount</span><span class="sxs-lookup"><span data-stu-id="02db7-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="02db7-103">Возвращает общее число элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="02db7-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02db7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02db7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02db7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="02db7-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="02db7-106">заполняет Указатель на общее число элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="02db7-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02db7-107">Требования</span><span class="sxs-lookup"><span data-stu-id="02db7-107">Requirements</span></span>  
 <span data-ttu-id="02db7-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02db7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02db7-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02db7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02db7-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02db7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02db7-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02db7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
