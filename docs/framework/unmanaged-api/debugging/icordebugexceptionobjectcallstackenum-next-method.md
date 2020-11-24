---
title: Метод ICorDebugExceptionObjectCallStackEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
ms.openlocfilehash: 17d5367564ec1ec98efc264ad9a5794c0d04a947
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672140"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="12bf0-102">Метод ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="12bf0-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>

<span data-ttu-id="12bf0-103">Возвращает указанное число экземпляров [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) , содержащих сведения из стека вызовов объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="12bf0-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12bf0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12bf0-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12bf0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12bf0-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="12bf0-106">окне Число извлекаемых экземпляров [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="12bf0-106">[in] The number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="12bf0-107">заполняет Массив указателей, каждый из которых указывает на объект [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="12bf0-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="12bf0-108">заполняет Указатель на число фактически возвращенных экземпляров [кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="12bf0-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12bf0-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="12bf0-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12bf0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="12bf0-110">Requirements</span></span>  

 <span data-ttu-id="12bf0-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12bf0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12bf0-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12bf0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12bf0-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12bf0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12bf0-114">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12bf0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12bf0-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="12bf0-115">See also</span></span>

- [<span data-ttu-id="12bf0-116">Интерфейс ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="12bf0-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="12bf0-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="12bf0-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
