---
title: Метод ICorDebugComObjectValue::GetCachedInterfaceTypes
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
ms.openlocfilehash: f5f0f11683043f1c287dd3ca3071830bcfb46502
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677561"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="9e590-102">Метод ICorDebugComObjectValue::GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="9e590-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>

<span data-ttu-id="9e590-103">Предоставляет перечислитель для типов интерфейса, которые текущий объект приводят к типу или используются в качестве.</span><span class="sxs-lookup"><span data-stu-id="9e590-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e590-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e590-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e590-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e590-105">Parameters</span></span>  

 `bIInspectableOnly`  
 <span data-ttu-id="9e590-106">окне Значение, указывающее, возвращает ли метод только среда выполнения Windows интерфейсы ( `IInspectable` интерфейсы) или все COM-интерфейсы, кэшированные вызываемой оболочкой времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="9e590-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="9e590-107">заполняет Указатель на адрес перечислителя ICorDebugTypeEnum, который предоставляет доступ к объектам ICorDebugType, представляющим кэшированные типы интерфейсов, отфильтрованные в соответствии с `bIInspectableOnly` .</span><span class="sxs-lookup"><span data-stu-id="9e590-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e590-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e590-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e590-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9e590-109">Requirements</span></span>  

 <span data-ttu-id="9e590-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e590-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e590-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e590-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e590-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e590-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e590-113">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e590-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e590-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9e590-114">See also</span></span>

- [<span data-ttu-id="9e590-115">Интерфейс ICorDebugComObjectValue Interface</span><span class="sxs-lookup"><span data-stu-id="9e590-115">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="9e590-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9e590-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
