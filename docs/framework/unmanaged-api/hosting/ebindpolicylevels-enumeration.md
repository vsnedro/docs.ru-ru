---
title: Перечисление EBindPolicyLevels
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
ms.openlocfilehash: 94d2ec12309249afbecdc4130f8fe20c927b0a9b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616376"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="94f7f-102">Перечисление EBindPolicyLevels</span><span class="sxs-lookup"><span data-stu-id="94f7f-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="94f7f-103">Предоставляет флаги для указания уровня применения или изменения политики сборки.</span><span class="sxs-lookup"><span data-stu-id="94f7f-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94f7f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94f7f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="94f7f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="94f7f-105">Members</span></span>  
  
|<span data-ttu-id="94f7f-106">Член</span><span class="sxs-lookup"><span data-stu-id="94f7f-106">Member</span></span>|<span data-ttu-id="94f7f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="94f7f-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="94f7f-108">Указывает, что политику следует применять на уровне администратора.</span><span class="sxs-lookup"><span data-stu-id="94f7f-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="94f7f-109">Указывает, что политику следует применять на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="94f7f-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="94f7f-110">Указывает, что политику следует применять на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="94f7f-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="94f7f-111">Указывает отсутствие флагов уровня политики.</span><span class="sxs-lookup"><span data-stu-id="94f7f-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="94f7f-112">Указывает, что политика должна применяться на уровне издателя.</span><span class="sxs-lookup"><span data-stu-id="94f7f-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="94f7f-113">Указывает, что политика должна быть применима на уровнях переменных.</span><span class="sxs-lookup"><span data-stu-id="94f7f-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="94f7f-114">Указывает, что политика должна поддерживать переносимость между реализациями сборки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="94f7f-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="94f7f-115">См. раздел файл конфигурации [ \< тег supportportability>](../../configure-apps/file-schema/runtime/supportportability-element.md) .</span><span class="sxs-lookup"><span data-stu-id="94f7f-115">See the [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="94f7f-116">Указывает, что политика должна быть унифицированной для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="94f7f-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94f7f-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="94f7f-117">Remarks</span></span>  
 <span data-ttu-id="94f7f-118">Это перечисление передается методам интерфейса [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) для указания изменений в политике приложения.</span><span class="sxs-lookup"><span data-stu-id="94f7f-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94f7f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="94f7f-119">Requirements</span></span>  
 <span data-ttu-id="94f7f-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94f7f-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94f7f-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="94f7f-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94f7f-122">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="94f7f-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94f7f-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94f7f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f7f-124">См. также статью</span><span class="sxs-lookup"><span data-stu-id="94f7f-124">See also</span></span>

- [<span data-ttu-id="94f7f-125">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="94f7f-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="94f7f-126">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="94f7f-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
