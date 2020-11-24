---
title: Структура AssemblyBindInfo
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
ms.openlocfilehash: d2ba7d8e66472f771a932a2dfb05bb9e1ee96290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685881"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="77969-102">Структура AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="77969-102">AssemblyBindInfo Structure</span></span>

<span data-ttu-id="77969-103">Предоставляет подробные сведения о сборке, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="77969-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77969-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77969-104">Syntax</span></span>  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="77969-105">Члены</span><span class="sxs-lookup"><span data-stu-id="77969-105">Members</span></span>  
  
|<span data-ttu-id="77969-106">Член</span><span class="sxs-lookup"><span data-stu-id="77969-106">Member</span></span>|<span data-ttu-id="77969-107">Описание</span><span class="sxs-lookup"><span data-stu-id="77969-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="77969-108">Уникальный идентификатор для, `IStream` возвращаемого вызовом метода [IHostAssemblyStore::P ровидеассембли](ihostassemblystore-provideassembly-method.md), из которого загружается сборка, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="77969-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="77969-109">Уникальный идентификатор сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="77969-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="77969-110">Идентификатор сборки, на которую указывает ссылка, после применения любых значений политики привязки.</span><span class="sxs-lookup"><span data-stu-id="77969-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="77969-111">Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее, какие политики управления версиями должны применяться к сборке, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="77969-111">One of the [EPolicyAction](epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77969-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="77969-112">Remarks</span></span>  

 <span data-ttu-id="77969-113">Узел предоставляет уникальный идентификатор среде CLR `dwAppDomainId` .</span><span class="sxs-lookup"><span data-stu-id="77969-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="77969-114">После `IHostAssemblyStore::ProvideAssembly` возврата вызова среда выполнения использует идентификатор, чтобы определить, `IStream` сопоставлено ли содержимое объекта.</span><span class="sxs-lookup"><span data-stu-id="77969-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="77969-115">Если это так, среда выполнения загружает существующую копию вместо повторного сопоставления потока.</span><span class="sxs-lookup"><span data-stu-id="77969-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="77969-116">Среда выполнения также использует этот идентификатор в качестве ключа поиска для потоков, возвращаемых из вызовов [IHostAssemblyStore::P ровидемодуле](ihostassemblystore-providemodule-method.md).</span><span class="sxs-lookup"><span data-stu-id="77969-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="77969-117">Таким образом, идентификатор должен быть уникальным для запросов модуля и для запросов сборки.</span><span class="sxs-lookup"><span data-stu-id="77969-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77969-118">Требования</span><span class="sxs-lookup"><span data-stu-id="77969-118">Requirements</span></span>  

 <span data-ttu-id="77969-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77969-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77969-120">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="77969-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="77969-121">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77969-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77969-122">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77969-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77969-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="77969-123">See also</span></span>

- [<span data-ttu-id="77969-124">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="77969-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="77969-125">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="77969-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="77969-126">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="77969-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="77969-127">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="77969-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="77969-128">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="77969-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="77969-129">Структура ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="77969-129">ModuleBindInfo Structure</span></span>](modulebindinfo-structure.md)
