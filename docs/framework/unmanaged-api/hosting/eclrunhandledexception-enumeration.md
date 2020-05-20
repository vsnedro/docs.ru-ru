---
title: Перечисление EClrUnhandledException
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: 63b07dda2293d3e05bd3c8fcdc45f20a498ea54c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616311"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="c1f22-102">Перечисление EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="c1f22-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="c1f22-103">Описывает доступные параметры для управления исключениями, которые не обрабатываются в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="c1f22-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1f22-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1f22-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="c1f22-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c1f22-105">Members</span></span>  
  
|<span data-ttu-id="c1f22-106">Член</span><span class="sxs-lookup"><span data-stu-id="c1f22-106">Member</span></span>|<span data-ttu-id="c1f22-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c1f22-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="c1f22-108">Указывает, что происходит поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c1f22-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="c1f22-109">Процесс разорван.</span><span class="sxs-lookup"><span data-stu-id="c1f22-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="c1f22-110">Указывает, что среда CLR не обрабатывает необработанные исключения и позволяет узлу определить дальнейшие действия.</span><span class="sxs-lookup"><span data-stu-id="c1f22-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1f22-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c1f22-111">Remarks</span></span>  
 <span data-ttu-id="c1f22-112">Чтобы указать, что среда CLR работает как более ранние версии, используйте `eHostDeterminedPolicy` член.</span><span class="sxs-lookup"><span data-stu-id="c1f22-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1f22-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c1f22-113">Requirements</span></span>  
 <span data-ttu-id="c1f22-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1f22-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1f22-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c1f22-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1f22-116">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c1f22-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1f22-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1f22-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f22-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c1f22-118">See also</span></span>

- [<span data-ttu-id="c1f22-119">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="c1f22-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="c1f22-120">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="c1f22-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="c1f22-121">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c1f22-121">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="c1f22-122">Метод SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="c1f22-122">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="c1f22-123">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c1f22-123">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="c1f22-124">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="c1f22-124">Hosting Enumerations</span></span>](hosting-enumerations.md)
