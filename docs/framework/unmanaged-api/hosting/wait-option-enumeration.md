---
title: Перечисление WAIT_OPTION
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 4c57a3fde3565a21800c60794b6c2d1c7616ddd8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008005"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="9d2e8-102">Перечисление WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="9d2e8-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="9d2e8-103">Содержит значения, указывающие действие, которое должен выполнить узел при выполнении операции, запрашиваемой блоками среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d2e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d2e8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="9d2e8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9d2e8-105">Members</span></span>  
  
|<span data-ttu-id="9d2e8-106">Член</span><span class="sxs-lookup"><span data-stu-id="9d2e8-106">Member</span></span>|<span data-ttu-id="9d2e8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9d2e8-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="9d2e8-108">Уведомляет узел о том, что задача должна быть пробуждена, если среда CLR вызывает метод [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9d2e8-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="9d2e8-109">Уведомляет узел о том, что он должен передавать сообщения в текущем потоке операционной системы, если поток блокируется.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="9d2e8-110">Среда выполнения задает это значение только в <xref:System.Threading.ApartmentState.STA> потоке.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="9d2e8-111">Сообщает узлу, что указанный запрос на синхронизацию не может быть разбит узлом.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="9d2e8-112">Это значит, что узел не может вернуть `HOST_E_DEADLOCK` .</span><span class="sxs-lookup"><span data-stu-id="9d2e8-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d2e8-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d2e8-113">Remarks</span></span>  
 <span data-ttu-id="9d2e8-114">Методы [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) и [IHostTaskManager:: свитчтотаск](ihosttaskmanager-switchtotask-method.md) принимают параметр этого типа.</span><span class="sxs-lookup"><span data-stu-id="9d2e8-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d2e8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="9d2e8-115">Requirements</span></span>  
 <span data-ttu-id="9d2e8-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d2e8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d2e8-117">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9d2e8-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9d2e8-118">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9d2e8-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d2e8-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d2e8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d2e8-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="9d2e8-120">See also</span></span>

- [<span data-ttu-id="9d2e8-121">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="9d2e8-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
