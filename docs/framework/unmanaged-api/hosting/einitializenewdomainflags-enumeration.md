---
title: Перечисление EInitializeNewDomainFlags
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: 7ff10f84d8d270d31c5d560fb3c9bd3c81cf3e24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616233"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="c8bb0-102">Перечисление EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="c8bb0-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="c8bb0-103">Позволяет узлу предоставлять среде выполнения сведения об инициализации домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c8bb0-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8bb0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8bb0-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c8bb0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c8bb0-105">Members</span></span>  
  
|<span data-ttu-id="c8bb0-106">Член</span><span class="sxs-lookup"><span data-stu-id="c8bb0-106">Member</span></span>|<span data-ttu-id="c8bb0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c8bb0-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="c8bb0-108">Флаги отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="c8bb0-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="c8bb0-109">Информирует среду CLR о том, что узел не будет вносить изменения в состояние безопасности домена приложения в <xref:System.AppDomainManager.InitializeNewDomain%2A> методе.</span><span class="sxs-lookup"><span data-stu-id="c8bb0-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8bb0-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c8bb0-110">Remarks</span></span>  
 <span data-ttu-id="c8bb0-111">Метод [иклрдомаинманажер:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) принимает параметр типа `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="c8bb0-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8bb0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c8bb0-112">Requirements</span></span>  
 <span data-ttu-id="c8bb0-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8bb0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8bb0-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c8bb0-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8bb0-115">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c8bb0-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8bb0-116">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8bb0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8bb0-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c8bb0-117">See also</span></span>

- [<span data-ttu-id="c8bb0-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="c8bb0-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="c8bb0-119">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="c8bb0-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
