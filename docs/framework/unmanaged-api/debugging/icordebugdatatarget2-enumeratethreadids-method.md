---
title: Метод ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 31a839076b34901ae1a8f3b43021f64f77629fc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713851"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="738de-102">Метод ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="738de-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>

<span data-ttu-id="738de-103">Возвращает список идентификаторов активных потоков.</span><span class="sxs-lookup"><span data-stu-id="738de-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="738de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="738de-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="738de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="738de-105">Parameters</span></span>  

 <span data-ttu-id="738de-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="738de-106">cThreadIDs</span></span>  
 <span data-ttu-id="738de-107">[входной] Максимальное число потоков, идентификаторы которых могут быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="738de-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="738de-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="738de-108">pcThreadIds</span></span>  
 <span data-ttu-id="738de-109">[выходной] Указатель на `ULONG32`, который указывает фактическое количество идентификаторов потоков, записанных в массив `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="738de-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="738de-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="738de-110">pThreadIDs</span></span>  
 <span data-ttu-id="738de-111">Массив идентификаторов потоков.</span><span class="sxs-lookup"><span data-stu-id="738de-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="738de-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="738de-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="738de-113">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="738de-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="738de-114">Требования</span><span class="sxs-lookup"><span data-stu-id="738de-114">Requirements</span></span>  

 <span data-ttu-id="738de-115">**Платформы:** См. раздел [требования к системе](../../get-started/system-requirements.md). **Заголовок:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="738de-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="738de-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="738de-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="738de-117">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="738de-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738de-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="738de-118">See also</span></span>

- [<span data-ttu-id="738de-119">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="738de-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="738de-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="738de-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
