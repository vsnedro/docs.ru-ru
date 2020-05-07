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
ms.openlocfilehash: ddcb8064dfb9be30c66404a8762a9ca73cd6afe4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860658"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="d29bd-102">Интерфейс ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="d29bd-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="d29bd-103">Предоставляет метод обратного вызова для [иклрдатаенуммеморирегионс:: енуммеморирегионс](iclrdataenummemoryregions-enummemoryregions-method.md) , сообщающий отладчику результат попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="d29bd-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d29bd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d29bd-104">Methods</span></span>  
  
|<span data-ttu-id="d29bd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d29bd-105">Method</span></span>|<span data-ttu-id="d29bd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d29bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d29bd-107">Метод EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="d29bd-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="d29bd-108">Вызывается `ICLRDataEnumMemoryRegions::EnumMemoryRegions` с помощью для передачи в отладчик результата попытки перечисления заданной области памяти.</span><span class="sxs-lookup"><span data-stu-id="d29bd-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d29bd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d29bd-109">Requirements</span></span>  
 <span data-ttu-id="d29bd-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d29bd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d29bd-111">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="d29bd-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d29bd-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d29bd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d29bd-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d29bd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d29bd-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d29bd-114">See also</span></span>

- [<span data-ttu-id="d29bd-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d29bd-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
