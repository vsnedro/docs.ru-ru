---
title: Интерфейс ICLRGCManager2
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
ms.openlocfilehash: d2873b5e1f8229e8a16dfaacf1c9737ac47405bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672803"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="89213-102">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="89213-102">ICLRGCManager2 Interface</span></span>

<span data-ttu-id="89213-103">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="89213-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89213-104">Методы</span><span class="sxs-lookup"><span data-stu-id="89213-104">Methods</span></span>  
  
|<span data-ttu-id="89213-105">Метод</span><span class="sxs-lookup"><span data-stu-id="89213-105">Method</span></span>|<span data-ttu-id="89213-106">Описание</span><span class="sxs-lookup"><span data-stu-id="89213-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89213-107">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="89213-107">SetGCStartupLimitsEx Method</span></span>](iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="89213-108">Задает размер сегмента сборки мусора и максимальный размер поколения 0 для системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="89213-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="89213-109">Включает поколение 0 и размеры сегментов, превышающие `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="89213-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89213-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="89213-110">Remarks</span></span>  

 <span data-ttu-id="89213-111">Этот интерфейс наследуется от [интерфейса иклргкманажер](iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="89213-111">This interface inherits from the [ICLRGCManager Interface](iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="89213-112">Среда CLR реализует механизм сборки мусора для управляемого <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="89213-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="89213-113">Дополнительные сведения о системе сборки мусора см. в разделе [сборка мусора](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="89213-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89213-114">Требования</span><span class="sxs-lookup"><span data-stu-id="89213-114">Requirements</span></span>  

 <span data-ttu-id="89213-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89213-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89213-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="89213-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89213-117">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89213-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89213-118">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89213-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89213-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="89213-119">See also</span></span>

- [<span data-ttu-id="89213-120">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="89213-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="89213-121">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="89213-121">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="89213-122">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="89213-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="89213-123">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="89213-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="89213-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="89213-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="89213-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="89213-125">Hosting</span></span>](index.md)
