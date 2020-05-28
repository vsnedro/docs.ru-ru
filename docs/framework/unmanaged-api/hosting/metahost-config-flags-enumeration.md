---
title: Перечисление METAHOST_CONFIG_FLAGS
ms.date: 03/30/2017
api_name:
- METAHOST_CONFIG_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_CONFIG_FLAGS
helpviewer_keywords:
- METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type:
- apiref
ms.openlocfilehash: a15c912cdf0eef1b8f131e8425ad9b5b01289982
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006731"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="29365-102">Перечисление METAHOST_CONFIG_FLAGS</span><span class="sxs-lookup"><span data-stu-id="29365-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="29365-103">Описывает возможные флаги, возвращаемые в `pdwConfigFlags` параметре метода [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , который указывает на присутствие и настройку `useLegacyV2RuntimeActivationPolicy` атрибута в [ \<startup> элементе](../../configure-apps/file-schema/startup/startup-element.md) файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="29365-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29365-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29365-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="29365-105">Участники</span><span class="sxs-lookup"><span data-stu-id="29365-105">Members</span></span>  
  
|<span data-ttu-id="29365-106">Член</span><span class="sxs-lookup"><span data-stu-id="29365-106">Member</span></span>|<span data-ttu-id="29365-107">Описание</span><span class="sxs-lookup"><span data-stu-id="29365-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="29365-108">`useLegacyV2RuntimeActivationPolicy`Атрибут не присутствовал в [ \<startup> элементе](../../configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="29365-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="29365-109">`useLegacyV2RuntimeActivationPolicy`Атрибут присутствовал и имеет значение `true` .</span><span class="sxs-lookup"><span data-stu-id="29365-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="29365-110">`useLegacyV2RuntimeActivationPolicy`Атрибут присутствовал и имеет значение `false` .</span><span class="sxs-lookup"><span data-stu-id="29365-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="29365-111">Примените эту маску к значению, возвращенному в `pdwConfigFlags` , чтобы получить значения, относящиеся к `useLegacyV2RuntimeActivationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="29365-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29365-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="29365-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29365-113">Требования</span><span class="sxs-lookup"><span data-stu-id="29365-113">Requirements</span></span>  
 <span data-ttu-id="29365-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29365-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29365-115">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="29365-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="29365-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="29365-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29365-117">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29365-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29365-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="29365-118">See also</span></span>

- [<span data-ttu-id="29365-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="29365-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="29365-120">Метод GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="29365-120">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="29365-121">\<startup>Дерев</span><span class="sxs-lookup"><span data-stu-id="29365-121">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
