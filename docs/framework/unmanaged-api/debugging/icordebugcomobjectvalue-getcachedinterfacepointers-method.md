---
title: Метод ICorDebugComObjectValue::GetCachedInterfacePointers
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
ms.openlocfilehash: fa22c17ed7d5bcd689f21d2d855d9be7a6a8e164
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892808"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a><span data-ttu-id="59803-102">Метод ICorDebugComObjectValue::GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="59803-102">ICorDebugComObjectValue::GetCachedInterfacePointers Method</span></span>
<span data-ttu-id="59803-103">Возвращает необработанные указатели интерфейса, кэшированные в текущей вызываемой оболочке времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="59803-103">Gets the raw interface pointers cached on the current runtime callable wrapper (RCW).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59803-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59803-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59803-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="59803-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="59803-106">окне Значение, указывающее, будет ли метод возвращать только среда выполнения Windows интерфейсы (`IInspectable` интерфейсы) или все COM-интерфейсы, которые кэшируются вызываемой оболочкой времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="59803-106">[in] A value that indicates whether the method will return only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces that are cached by the runtime callable wrapper (RCW).</span></span>  
  
 `celt`  
 <span data-ttu-id="59803-107">окне Число объектов, адреса которых необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="59803-107">[in] The number of objects whose addresses are to be retrieved.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="59803-108">заполняет Указатель на число `CORDB_ADDRESS` значений, фактически возвращаемых в `ptrs`.</span><span class="sxs-lookup"><span data-stu-id="59803-108">[out] A pointer to the number of `CORDB_ADDRESS` values actually returned in `ptrs`.</span></span>  
  
 `ptrs`  
 <span data-ttu-id="59803-109">Указатель на начальный адрес массива `CORDB_ADDRESS` значений, содержащих адреса кэшированных объектов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="59803-109">A pointer to the starting address of an array of `CORDB_ADDRESS` values that contain the addresses of cached interface objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59803-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="59803-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59803-111">Требования</span><span class="sxs-lookup"><span data-stu-id="59803-111">Requirements</span></span>  
 <span data-ttu-id="59803-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59803-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59803-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59803-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59803-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59803-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59803-115">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59803-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59803-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="59803-116">See also</span></span>

- [<span data-ttu-id="59803-117">Интерфейс ICorDebugComObjectValue Interface</span><span class="sxs-lookup"><span data-stu-id="59803-117">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="59803-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="59803-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
