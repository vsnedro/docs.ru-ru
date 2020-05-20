---
title: Перечисление EContextType
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
ms.openlocfilehash: ceb68410e808bf7843149e3f05a39c7a98d0c000
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616298"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="6dc7a-102">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="6dc7a-102">EContextType Enumeration</span></span>
<span data-ttu-id="6dc7a-103">Описывает контекст безопасности выполняющегося в данный момент потока.</span><span class="sxs-lookup"><span data-stu-id="6dc7a-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dc7a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6dc7a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="6dc7a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="6dc7a-105">Members</span></span>  
  
|<span data-ttu-id="6dc7a-106">Член</span><span class="sxs-lookup"><span data-stu-id="6dc7a-106">Member</span></span>|<span data-ttu-id="6dc7a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6dc7a-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="6dc7a-108">Указывает контекст текущего потока во время вызова средой CLR метода [IHostSecurityManager:: getsecuritycontext-](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) или контекста, ЗАПРАШИВАЕМого средой CLR при вызове метода [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6dc7a-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="6dc7a-109">Указывает контекст, для которого узел имеет более низкий уровень привилегий, например сборщик мусора, конструктор класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="6dc7a-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dc7a-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6dc7a-110">Remarks</span></span>  
 <span data-ttu-id="6dc7a-111">Среда CLR предоставляет одно из `EContextType` значений в качестве значения параметра в вызовах `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` методов и.</span><span class="sxs-lookup"><span data-stu-id="6dc7a-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dc7a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6dc7a-112">Requirements</span></span>  
 <span data-ttu-id="6dc7a-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dc7a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dc7a-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6dc7a-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6dc7a-115">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6dc7a-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6dc7a-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dc7a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc7a-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="6dc7a-117">See also</span></span>

- [<span data-ttu-id="6dc7a-118">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="6dc7a-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="6dc7a-119">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="6dc7a-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="6dc7a-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="6dc7a-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
