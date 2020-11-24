---
title: Метод ICLRAssemblyReferenceList::IsAssemblyReferenceInList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
ms.openlocfilehash: f74e0f111ff7869d0bfed61d420f3788f65876dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679160"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="cb07b-102">Метод ICLRAssemblyReferenceList::IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="cb07b-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>

<span data-ttu-id="cb07b-103">Возвращает значение, указывающее, ссылается ли заданный указатель на сборку в списке.</span><span class="sxs-lookup"><span data-stu-id="cb07b-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb07b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb07b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb07b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb07b-105">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="cb07b-106">окне Указатель интерфейса на сборку, для которой необходимо выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="cb07b-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="cb07b-107">Допустимые значения имеют тип `IAssemblyName` или `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="cb07b-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb07b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cb07b-108">Return Value</span></span>  
  
|<span data-ttu-id="cb07b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cb07b-109">HRESULT</span></span>|<span data-ttu-id="cb07b-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="cb07b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cb07b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cb07b-111">S_OK</span></span>|<span data-ttu-id="cb07b-112">Строка появится в списке.</span><span class="sxs-lookup"><span data-stu-id="cb07b-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="cb07b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="cb07b-113">S_FALSE</span></span>|<span data-ttu-id="cb07b-114">Строка не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="cb07b-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="cb07b-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cb07b-115">E_FAIL</span></span>|<span data-ttu-id="cb07b-116">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="cb07b-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cb07b-117">После того как метод возвращает E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="cb07b-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="cb07b-118">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cb07b-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb07b-119">Требования</span><span class="sxs-lookup"><span data-stu-id="cb07b-119">Requirements</span></span>  

 <span data-ttu-id="cb07b-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb07b-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb07b-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cb07b-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb07b-122">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb07b-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb07b-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb07b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb07b-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cb07b-124">See also</span></span>

- [<span data-ttu-id="cb07b-125">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="cb07b-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="cb07b-126">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="cb07b-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="cb07b-127">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="cb07b-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="cb07b-128">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="cb07b-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
