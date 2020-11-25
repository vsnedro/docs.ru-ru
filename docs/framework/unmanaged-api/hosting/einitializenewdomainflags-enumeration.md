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
ms.openlocfilehash: 8350b507609e63c060cda08514200d386c37a6b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724329"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="84914-102">Перечисление EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="84914-102">EInitializeNewDomainFlags Enumeration</span></span>

<span data-ttu-id="84914-103">Позволяет узлу предоставлять среде выполнения сведения об инициализации домена приложения.</span><span class="sxs-lookup"><span data-stu-id="84914-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84914-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84914-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="84914-105">Члены</span><span class="sxs-lookup"><span data-stu-id="84914-105">Members</span></span>  
  
|<span data-ttu-id="84914-106">Член</span><span class="sxs-lookup"><span data-stu-id="84914-106">Member</span></span>|<span data-ttu-id="84914-107">Описание</span><span class="sxs-lookup"><span data-stu-id="84914-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="84914-108">Флаги отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="84914-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="84914-109">Информирует среду CLR о том, что узел не будет вносить изменения в состояние безопасности домена приложения в <xref:System.AppDomainManager.InitializeNewDomain%2A> методе.</span><span class="sxs-lookup"><span data-stu-id="84914-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84914-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="84914-110">Remarks</span></span>  

 <span data-ttu-id="84914-111">Метод [иклрдомаинманажер:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) принимает параметр типа `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="84914-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84914-112">Требования</span><span class="sxs-lookup"><span data-stu-id="84914-112">Requirements</span></span>  

 <span data-ttu-id="84914-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84914-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84914-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="84914-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84914-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84914-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84914-116">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84914-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84914-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84914-117">See also</span></span>

- [<span data-ttu-id="84914-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="84914-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="84914-119">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="84914-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
