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
ms.openlocfilehash: b93b27957cc715a5b4718dd9ef61cd11f4a39914
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493424"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="ed89c-102">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="ed89c-102">EContextType Enumeration</span></span>
<span data-ttu-id="ed89c-103">Описывает контекст безопасности выполняющегося в данный момент потока.</span><span class="sxs-lookup"><span data-stu-id="ed89c-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed89c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed89c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="ed89c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ed89c-105">Members</span></span>  
  
|<span data-ttu-id="ed89c-106">Член</span><span class="sxs-lookup"><span data-stu-id="ed89c-106">Member</span></span>|<span data-ttu-id="ed89c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ed89c-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="ed89c-108">Указывает контекст текущего потока во время вызова средой CLR метода [IHostSecurityManager:: getsecuritycontext-](ihostsecuritymanager-getsecuritycontext-method.md) или контекста, ЗАПРАШИВАЕМого средой CLR при вызове метода [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ed89c-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="ed89c-109">Указывает контекст, для которого узел имеет более низкий уровень привилегий, например сборщик мусора, конструктор класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="ed89c-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed89c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed89c-110">Remarks</span></span>  
 <span data-ttu-id="ed89c-111">Среда CLR предоставляет одно из `EContextType` значений в качестве значения параметра в вызовах `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` методов и.</span><span class="sxs-lookup"><span data-stu-id="ed89c-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed89c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ed89c-112">Requirements</span></span>  
 <span data-ttu-id="ed89c-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed89c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed89c-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ed89c-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed89c-115">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ed89c-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed89c-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed89c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed89c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ed89c-117">See also</span></span>

- [<span data-ttu-id="ed89c-118">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="ed89c-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="ed89c-119">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="ed89c-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="ed89c-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="ed89c-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
