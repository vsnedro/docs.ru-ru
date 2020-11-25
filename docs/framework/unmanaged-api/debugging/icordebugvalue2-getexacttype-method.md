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
ms.openlocfilehash: cb5bec66ab02de248109d8aaf444a93e67c2c6d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720364"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="c4e81-102">Метод ICorDebugValue2::GetExactType</span><span class="sxs-lookup"><span data-stu-id="c4e81-102">ICorDebugValue2::GetExactType Method</span></span>

<span data-ttu-id="c4e81-103">Возвращает указатель интерфейса на объект "ICorDebugType", представляющий <xref:System.Type> это значение.</span><span class="sxs-lookup"><span data-stu-id="c4e81-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4e81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4e81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4e81-105">Parameters</span></span>  

 `ppType`  
 <span data-ttu-id="c4e81-106">заполняет Указатель на адрес `ICorDebugType` объекта, представляющий <xref:System.Type> значение, представленное этим объектом "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="c4e81-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4e81-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c4e81-107">Remarks</span></span>  

 <span data-ttu-id="c4e81-108">Метод с учетом универсальных шаблонов `GetExactType` заменяет методы [ICorDebugObjectValue::](icordebugobjectvalue-getclass-method.md) noreturn и [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , каждый из которых возвращает сведения о типе значения.</span><span class="sxs-lookup"><span data-stu-id="c4e81-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4e81-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c4e81-109">Requirements</span></span>  

 <span data-ttu-id="c4e81-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4e81-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e81-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4e81-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4e81-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4e81-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4e81-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4e81-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e81-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c4e81-114">See also</span></span>
