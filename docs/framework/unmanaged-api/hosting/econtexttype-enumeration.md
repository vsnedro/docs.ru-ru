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
ms.openlocfilehash: c6d1ace12bd07fa1f14c8570eca1f950a5c22be9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686336"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="dbf46-102">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="dbf46-102">EContextType Enumeration</span></span>

<span data-ttu-id="dbf46-103">Описывает контекст безопасности выполняющегося в данный момент потока.</span><span class="sxs-lookup"><span data-stu-id="dbf46-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbf46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbf46-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="dbf46-105">Члены</span><span class="sxs-lookup"><span data-stu-id="dbf46-105">Members</span></span>  
  
|<span data-ttu-id="dbf46-106">Член</span><span class="sxs-lookup"><span data-stu-id="dbf46-106">Member</span></span>|<span data-ttu-id="dbf46-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dbf46-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="dbf46-108">Указывает контекст текущего потока во время вызова средой CLR метода [IHostSecurityManager:: getsecuritycontext-](ihostsecuritymanager-getsecuritycontext-method.md) или контекста, ЗАПРАШИВАЕМого средой CLR при вызове метода [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dbf46-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="dbf46-109">Указывает контекст, для которого узел имеет более низкий уровень привилегий, например сборщик мусора, конструктор класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="dbf46-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbf46-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="dbf46-110">Remarks</span></span>  

 <span data-ttu-id="dbf46-111">Среда CLR предоставляет одно из `EContextType` значений в качестве значения параметра в вызовах `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` методов и.</span><span class="sxs-lookup"><span data-stu-id="dbf46-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbf46-112">Требования</span><span class="sxs-lookup"><span data-stu-id="dbf46-112">Requirements</span></span>  

 <span data-ttu-id="dbf46-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbf46-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbf46-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dbf46-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbf46-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dbf46-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbf46-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbf46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf46-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dbf46-117">See also</span></span>

- [<span data-ttu-id="dbf46-118">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="dbf46-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="dbf46-119">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="dbf46-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="dbf46-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="dbf46-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
