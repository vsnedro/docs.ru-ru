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
ms.openlocfilehash: 0f3ecc0d497eaee937647df47ba0956335a2fe41
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703942"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="01dc7-102">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="01dc7-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="01dc7-103">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="01dc7-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01dc7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="01dc7-104">Methods</span></span>  
  
|<span data-ttu-id="01dc7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="01dc7-105">Method</span></span>|<span data-ttu-id="01dc7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="01dc7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01dc7-107">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="01dc7-107">SetGCStartupLimitsEx Method</span></span>](iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="01dc7-108">Задает размер сегмента сборки мусора и максимальный размер поколения 0 для системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="01dc7-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="01dc7-109">Включает поколение 0 и размеры сегментов, превышающие `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="01dc7-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01dc7-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="01dc7-110">Remarks</span></span>  
 <span data-ttu-id="01dc7-111">Этот интерфейс наследуется от [интерфейса иклргкманажер](iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="01dc7-111">This interface inherits from the [ICLRGCManager Interface](iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="01dc7-112">Среда CLR реализует механизм сборки мусора для управляемого <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="01dc7-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="01dc7-113">Дополнительные сведения о системе сборки мусора см. в разделе [сборка мусора](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="01dc7-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01dc7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="01dc7-114">Requirements</span></span>  
 <span data-ttu-id="01dc7-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01dc7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01dc7-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="01dc7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01dc7-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="01dc7-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01dc7-118">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01dc7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01dc7-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="01dc7-119">See also</span></span>

- [<span data-ttu-id="01dc7-120">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="01dc7-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="01dc7-121">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="01dc7-121">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="01dc7-122">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="01dc7-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="01dc7-123">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="01dc7-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="01dc7-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="01dc7-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="01dc7-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="01dc7-125">Hosting</span></span>](index.md)
