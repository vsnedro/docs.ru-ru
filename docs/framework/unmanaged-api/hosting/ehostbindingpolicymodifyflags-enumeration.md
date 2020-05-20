---
title: Перечисление EHostBindingPolicyModifyFlags
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
ms.openlocfilehash: 256c362ae0aea51fea16ce799db243b105dee81a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616246"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="891e0-102">Перечисление EHostBindingPolicyModifyFlags</span><span class="sxs-lookup"><span data-stu-id="891e0-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="891e0-103">Позволяет узлу указать тип перенаправления, которое должна выполнять среда CLR при применении изменений политики из исходной сборки к целевой сборке.</span><span class="sxs-lookup"><span data-stu-id="891e0-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="891e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="891e0-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="891e0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="891e0-105">Members</span></span>  
  
|<span data-ttu-id="891e0-106">Член</span><span class="sxs-lookup"><span data-stu-id="891e0-106">Member</span></span>|<span data-ttu-id="891e0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="891e0-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="891e0-108">Указывает, что среда CLR будет связывать значения политики исходной сборки с целевыми сборками.</span><span class="sxs-lookup"><span data-stu-id="891e0-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="891e0-109">Указывает, что среда CLR будет выполнять действие по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="891e0-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="891e0-110">Указывает, что среда CLR будет задавать максимальные значения политики для целевой сборки.</span><span class="sxs-lookup"><span data-stu-id="891e0-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="891e0-111">Указывает, что среда CLR заменит значения политики целевой сборки значениями из исходной сборки.</span><span class="sxs-lookup"><span data-stu-id="891e0-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="891e0-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="891e0-112">Remarks</span></span>  
 <span data-ttu-id="891e0-113">Метод [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) принимает параметр типа `EHostBindingPolicyModifyFlags` .</span><span class="sxs-lookup"><span data-stu-id="891e0-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="891e0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="891e0-114">Requirements</span></span>  
 <span data-ttu-id="891e0-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="891e0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="891e0-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="891e0-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="891e0-117">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="891e0-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="891e0-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="891e0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891e0-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="891e0-119">See also</span></span>

- [<span data-ttu-id="891e0-120">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="891e0-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="891e0-121">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="891e0-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
