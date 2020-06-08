---
title: Метод ICorProfilerInfo5::GetEventMask2
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: 758e5b71443b127c80c820eb8531056530e81b13
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495701"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="6d22b-102">Метод ICorProfilerInfo5::GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="6d22b-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="6d22b-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="6d22b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6d22b-104">Получает текущие категории событий, о которых профилировщик хочет получать уведомления из среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6d22b-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="6d22b-105">Он предоставляет функциональные возможности, не предоставляемые методом [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6d22b-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d22b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d22b-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d22b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d22b-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="6d22b-108">[из] Указатель на 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="6d22b-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="6d22b-109">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="6d22b-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="6d22b-110">Биты описаны в перечислении [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6d22b-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="6d22b-111">[из] Указатель на 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="6d22b-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="6d22b-112">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="6d22b-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="6d22b-113">Биты описаны в перечислении [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6d22b-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d22b-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d22b-114">Remarks</span></span>  
 <span data-ttu-id="6d22b-115">Метод `GetEventMask2` используется для определения обратных вызовов, на которые подписался профилировщик.</span><span class="sxs-lookup"><span data-stu-id="6d22b-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="6d22b-116">Обычно выполняется логическое или для `pdwEventsLow` значений и, а также `pdwEventsHigh` все новые биты, которые необходимо задать, а затем вызывается метод [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6d22b-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="6d22b-117">Этот метод является рекомендуемым альтернативой методу [GetEventMask](icorprofilerinfo-geteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6d22b-117">This method is the recommended alternative to the [GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d22b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="6d22b-118">Requirements</span></span>  
 <span data-ttu-id="6d22b-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d22b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d22b-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d22b-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d22b-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d22b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d22b-122">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d22b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d22b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6d22b-123">See also</span></span>

- [<span data-ttu-id="6d22b-124">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="6d22b-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="6d22b-125">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="6d22b-125">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
