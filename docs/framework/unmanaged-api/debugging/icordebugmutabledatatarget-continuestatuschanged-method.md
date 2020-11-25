---
title: Метод ICorDebugMutableDataTarget::ContinueStatusChanged
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: 4910b125c2344505128a6979dfe4c9fad2b72c19
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695794"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="49d31-102">Метод ICorDebugMutableDataTarget::ContinueStatusChanged</span><span class="sxs-lookup"><span data-stu-id="49d31-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>

<span data-ttu-id="49d31-103">Изменяет состояние продолжения для незавершенных событий отладки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="49d31-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49d31-104">Syntax</span></span>  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49d31-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49d31-105">Parameters</span></span>  

 `dwThreadId`  
 <span data-ttu-id="49d31-106">Идентификатор потока, определяемый операционной системой.</span><span class="sxs-lookup"><span data-stu-id="49d31-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="49d31-107">Значение [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md), которое представляет новое запрошенное состояние продолжения.</span><span class="sxs-lookup"><span data-stu-id="49d31-107">A [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md) value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49d31-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="49d31-108">Remarks</span></span>  

 <span data-ttu-id="49d31-109">Отладчик вызывает метод `ContinueStatusChanged` при вызове метода ICorDebug, требующего, чтобы способ обработки текущего события отладки потенциально отличался от способа, которым оно обычно обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="49d31-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="49d31-110">Например, если имеется незавершенное исключение и отладчик запрашивает операцию, которая будет отменять это исключение (например, [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) или `FuncEval`), этот API используется для запроса отмены исключения.</span><span class="sxs-lookup"><span data-stu-id="49d31-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49d31-111">Требования</span><span class="sxs-lookup"><span data-stu-id="49d31-111">Requirements</span></span>  

 <span data-ttu-id="49d31-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49d31-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49d31-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49d31-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49d31-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49d31-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49d31-115">**.NET Framework версии:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49d31-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d31-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="49d31-116">See also</span></span>

- [<span data-ttu-id="49d31-117">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="49d31-117">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="49d31-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="49d31-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
