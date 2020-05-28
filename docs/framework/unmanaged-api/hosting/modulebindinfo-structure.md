---
title: Структура ModuleBindInfo
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: 31be0525c637e50c1161129277d651b56dadfaa3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006770"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="87551-102">Структура ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="87551-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="87551-103">Предоставляет подробные сведения о модуле, на который указывает ссылка, и содержащей его сборку.</span><span class="sxs-lookup"><span data-stu-id="87551-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87551-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87551-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="87551-105">Участники</span><span class="sxs-lookup"><span data-stu-id="87551-105">Members</span></span>  
  
|<span data-ttu-id="87551-106">Член</span><span class="sxs-lookup"><span data-stu-id="87551-106">Member</span></span>|<span data-ttu-id="87551-107">Описание</span><span class="sxs-lookup"><span data-stu-id="87551-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="87551-108">Уникальный идентификатор для `IStream` , возвращаемый вызовом метода [IHostAssemblyStore::P ровидемодуле](ihostassemblystore-providemodule-method.md) , из которого загружается указанный модуль.</span><span class="sxs-lookup"><span data-stu-id="87551-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="87551-109">Уникальный идентификатор сборки, содержащей упоминаемый модуль.</span><span class="sxs-lookup"><span data-stu-id="87551-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="87551-110">Имя модуля, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="87551-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87551-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="87551-111">Remarks</span></span>  
 <span data-ttu-id="87551-112">`ModuleBindInfo`передается в качестве параметра в `IHostAssemblyStore::ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="87551-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="87551-113">Узел предоставляет уникальный идентификатор среде CLR `dwAppDomainId` .</span><span class="sxs-lookup"><span data-stu-id="87551-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="87551-114">После вызова метода [IHostAssemblyStore::P ровидеассембли](ihostassemblystore-provideassembly-method.md) среда выполнения использует идентификатор, чтобы определить, `IStream` сопоставлено ли содержимое объекта.</span><span class="sxs-lookup"><span data-stu-id="87551-114">After a call to the [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="87551-115">Если это так, среда выполнения загружает существующую копию вместо повторного сопоставления потока.</span><span class="sxs-lookup"><span data-stu-id="87551-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="87551-116">Среда выполнения также использует этот идентификатор в качестве ключа поиска для потоков, возвращаемых из вызовов `IHostAssemblyStore::ProvideAssembly` метода.</span><span class="sxs-lookup"><span data-stu-id="87551-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="87551-117">Таким образом, идентификатор должен быть уникальным для запросов модуля, а также для запросов сборки.</span><span class="sxs-lookup"><span data-stu-id="87551-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87551-118">Требования</span><span class="sxs-lookup"><span data-stu-id="87551-118">Requirements</span></span>  
 <span data-ttu-id="87551-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87551-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87551-120">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="87551-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="87551-121">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="87551-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87551-122">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87551-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87551-123">См. также статью</span><span class="sxs-lookup"><span data-stu-id="87551-123">See also</span></span>

- [<span data-ttu-id="87551-124">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="87551-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="87551-125">Структура AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="87551-125">AssemblyBindInfo Structure</span></span>](assemblybindinfo-structure.md)
- [<span data-ttu-id="87551-126">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="87551-126">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="87551-127">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="87551-127">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="87551-128">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="87551-128">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
