---
title: Интерфейс ICLRDataEnumMemoryRegionsCallback
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: f080d852b190346740a3629f3b5d46a9f3808293
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703634"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="7a2a1-102">Интерфейс ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="7a2a1-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>

<span data-ttu-id="7a2a1-103">Предоставляет метод обратного вызова для [иклрдатаенуммеморирегионс:: енуммеморирегионс](iclrdataenummemoryregions-enummemoryregions-method.md) , сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="7a2a1-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a2a1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7a2a1-104">Methods</span></span>  
  
|<span data-ttu-id="7a2a1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7a2a1-105">Method</span></span>|<span data-ttu-id="7a2a1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7a2a1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7a2a1-107">Метод EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="7a2a1-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="7a2a1-108">Вызывается с помощью `ICLRDataEnumMemoryRegions::EnumMemoryRegions` для передачи в отладчик результата попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="7a2a1-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a2a1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7a2a1-109">Requirements</span></span>  

 <span data-ttu-id="7a2a1-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a2a1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a2a1-111">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="7a2a1-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7a2a1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a2a1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a2a1-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a2a1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a2a1-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7a2a1-114">See also</span></span>

- [<span data-ttu-id="7a2a1-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7a2a1-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
