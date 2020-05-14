---
title: Метод ICorDebugValue2::GetExactType
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: dcec97bac2aefc8db1f9351f1dacb0f36fc0d2a0
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396799"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="d0bc0-102">Метод ICorDebugValue2::GetExactType</span><span class="sxs-lookup"><span data-stu-id="d0bc0-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="d0bc0-103">Возвращает указатель интерфейса на объект "ICorDebugType", представляющий <xref:System.Type> это значение.</span><span class="sxs-lookup"><span data-stu-id="d0bc0-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0bc0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0bc0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0bc0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d0bc0-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="d0bc0-106">заполняет Указатель на адрес `ICorDebugType` объекта, представляющий <xref:System.Type> значение, представленное этим объектом "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="d0bc0-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0bc0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0bc0-107">Remarks</span></span>  
 <span data-ttu-id="d0bc0-108">Метод с учетом универсальных шаблонов `GetExactType` заменяет методы [ICorDebugObjectValue::](icordebugobjectvalue-getclass-method.md) noreturn и [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , каждый из которых возвращает сведения о типе значения.</span><span class="sxs-lookup"><span data-stu-id="d0bc0-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0bc0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d0bc0-109">Requirements</span></span>  
 <span data-ttu-id="d0bc0-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0bc0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0bc0-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0bc0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0bc0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0bc0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0bc0-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0bc0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0bc0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d0bc0-114">See also</span></span>
