---
title: Интерфейс ICorDebugValueBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
ms.openlocfilehash: 1183f9f6d1ac221b20767f0a1bab15b3e9665a61
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396611"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="4b11b-102">Интерфейс ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4b11b-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="4b11b-103">Расширяет интерфейс Икордебугбреакпоинт для предоставления доступа к конкретным значениям.</span><span class="sxs-lookup"><span data-stu-id="4b11b-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4b11b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4b11b-104">Methods</span></span>  
  
|<span data-ttu-id="4b11b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4b11b-105">Method</span></span>|<span data-ttu-id="4b11b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4b11b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4b11b-107">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="4b11b-107">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="4b11b-108">Возвращает указатель интерфейса на объект ICorDebugValue, представляющий значение объекта, для которого задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="4b11b-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b11b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b11b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b11b-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="4b11b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b11b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4b11b-111">Requirements</span></span>  
 <span data-ttu-id="4b11b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b11b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b11b-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b11b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b11b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b11b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b11b-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b11b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b11b-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4b11b-116">See also</span></span>

- [<span data-ttu-id="4b11b-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4b11b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
