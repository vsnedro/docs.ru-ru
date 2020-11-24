---
title: Интерфейс ICLRGCManager
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
ms.openlocfilehash: dbe3df6bb20e5ad8f9eb534a366405eb9c33984f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678250"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="abefc-102">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="abefc-102">ICLRGCManager Interface</span></span>

<span data-ttu-id="abefc-103">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="abefc-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="abefc-104">Начиная с .NET Framework 4,5, можно использовать метод [ICLRGCManager2:: SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) , чтобы задать размер сегмента сборки мусора и максимальный размер поколения 0 системы сборки мусора до значений, превышающих `DWORD` предельное значение, накладываемое методом [сетгкстартуплимитс](iclrgcmanager-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="abefc-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="abefc-105">Методы</span><span class="sxs-lookup"><span data-stu-id="abefc-105">Methods</span></span>  
  
|<span data-ttu-id="abefc-106">Метод</span><span class="sxs-lookup"><span data-stu-id="abefc-106">Method</span></span>|<span data-ttu-id="abefc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="abefc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="abefc-108">Метод Collect</span><span class="sxs-lookup"><span data-stu-id="abefc-108">Collect Method</span></span>](iclrgcmanager-collect-method.md)|<span data-ttu-id="abefc-109">Вызывает принудительную сборку мусора для указанного поколения.</span><span class="sxs-lookup"><span data-stu-id="abefc-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="abefc-110">Метод GetStats</span><span class="sxs-lookup"><span data-stu-id="abefc-110">GetStats Method</span></span>](iclrgcmanager-getstats-method.md)|<span data-ttu-id="abefc-111">Возвращает набор текущих статистических данных о системе сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="abefc-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="abefc-112">Метод SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="abefc-112">SetGCStartupLimits Method</span></span>](iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="abefc-113">Задает размер сегмента сборки мусора и максимальный размер поколения 0 для системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="abefc-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abefc-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="abefc-114">Remarks</span></span>  

 <span data-ttu-id="abefc-115">Среда CLR реализует механизм сборки мусора для управляемого <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="abefc-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="abefc-116">Дополнительные сведения о системе сборки мусора см. в разделе [сборка мусора](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="abefc-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abefc-117">Требования</span><span class="sxs-lookup"><span data-stu-id="abefc-117">Requirements</span></span>  

 <span data-ttu-id="abefc-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abefc-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abefc-119">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="abefc-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abefc-120">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abefc-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abefc-121">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abefc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abefc-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="abefc-122">See also</span></span>

- [<span data-ttu-id="abefc-123">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="abefc-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="abefc-124">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="abefc-124">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="abefc-125">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="abefc-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="abefc-126">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="abefc-126">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="abefc-127">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="abefc-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="abefc-128">Размещение</span><span class="sxs-lookup"><span data-stu-id="abefc-128">Hosting</span></span>](index.md)
