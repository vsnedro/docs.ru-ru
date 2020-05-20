---
title: Перечисление EMemoryAvailable
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: 822396e28d000a5309738680fec502e1aeacd67c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616220"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="02908-102">Перечисление EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="02908-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="02908-103">Содержит значения, указывающие объем свободной физической памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="02908-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="02908-104">Эти значения логически сопоставляются с событиями для высокой и нехватки памяти, возвращаемой `CreateMemoryResourceNotification` функцией в Windows API.</span><span class="sxs-lookup"><span data-stu-id="02908-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02908-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02908-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="02908-106">Участники</span><span class="sxs-lookup"><span data-stu-id="02908-106">Members</span></span>  
  
|<span data-ttu-id="02908-107">Член</span><span class="sxs-lookup"><span data-stu-id="02908-107">Member</span></span>|<span data-ttu-id="02908-108">Описание</span><span class="sxs-lookup"><span data-stu-id="02908-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="02908-109">Доступно достаточно физической памяти.</span><span class="sxs-lookup"><span data-stu-id="02908-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="02908-110">Доступно очень мало физической памяти.</span><span class="sxs-lookup"><span data-stu-id="02908-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="02908-111">Доступная физическая память не является нейтральной.</span><span class="sxs-lookup"><span data-stu-id="02908-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02908-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="02908-112">Remarks</span></span>  
 <span data-ttu-id="02908-113">Это значение передается узлом в среду CLR с помощью вызова метода [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="02908-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02908-114">Требования</span><span class="sxs-lookup"><span data-stu-id="02908-114">Requirements</span></span>  
 <span data-ttu-id="02908-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02908-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02908-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="02908-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02908-117">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="02908-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02908-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02908-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02908-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="02908-119">See also</span></span>

- [<span data-ttu-id="02908-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="02908-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
