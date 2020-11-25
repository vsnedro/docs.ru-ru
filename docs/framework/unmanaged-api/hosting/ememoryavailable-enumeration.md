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
ms.openlocfilehash: 6a8765bfd62a2e6543661804ab8d009ce19f8813
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724316"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="64dfc-102">Перечисление EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="64dfc-102">EMemoryAvailable Enumeration</span></span>

<span data-ttu-id="64dfc-103">Содержит значения, указывающие объем свободной физической памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="64dfc-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="64dfc-104">Эти значения логически сопоставляются с событиями для высокой и нехватки памяти, возвращаемой `CreateMemoryResourceNotification` функцией в Windows API.</span><span class="sxs-lookup"><span data-stu-id="64dfc-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64dfc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64dfc-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="64dfc-106">Члены</span><span class="sxs-lookup"><span data-stu-id="64dfc-106">Members</span></span>  
  
|<span data-ttu-id="64dfc-107">Член</span><span class="sxs-lookup"><span data-stu-id="64dfc-107">Member</span></span>|<span data-ttu-id="64dfc-108">Описание</span><span class="sxs-lookup"><span data-stu-id="64dfc-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="64dfc-109">Доступно достаточно физической памяти.</span><span class="sxs-lookup"><span data-stu-id="64dfc-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="64dfc-110">Доступно очень мало физической памяти.</span><span class="sxs-lookup"><span data-stu-id="64dfc-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="64dfc-111">Доступная физическая память не является нейтральной.</span><span class="sxs-lookup"><span data-stu-id="64dfc-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64dfc-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="64dfc-112">Remarks</span></span>  

 <span data-ttu-id="64dfc-113">Это значение передается узлом в среду CLR с помощью вызова метода [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="64dfc-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64dfc-114">Требования</span><span class="sxs-lookup"><span data-stu-id="64dfc-114">Requirements</span></span>  

 <span data-ttu-id="64dfc-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64dfc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64dfc-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="64dfc-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64dfc-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64dfc-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64dfc-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64dfc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64dfc-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="64dfc-119">See also</span></span>

- [<span data-ttu-id="64dfc-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="64dfc-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
