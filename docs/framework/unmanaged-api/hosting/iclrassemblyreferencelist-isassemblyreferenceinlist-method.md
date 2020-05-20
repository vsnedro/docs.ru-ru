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
ms.openlocfilehash: 0632a7f5feee87c386d9488a6c989413af68a47f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615895"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="ee5dc-102">Метод ICLRAssemblyReferenceList::IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="ee5dc-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="ee5dc-103">Возвращает значение, указывающее, ссылается ли заданный указатель на сборку в списке.</span><span class="sxs-lookup"><span data-stu-id="ee5dc-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee5dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee5dc-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee5dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee5dc-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="ee5dc-106">окне Указатель интерфейса на сборку, для которой необходимо выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="ee5dc-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="ee5dc-107">Допустимые значения имеют тип `IAssemblyName` или `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="ee5dc-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee5dc-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ee5dc-108">Return Value</span></span>  
  
|<span data-ttu-id="ee5dc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee5dc-109">HRESULT</span></span>|<span data-ttu-id="ee5dc-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ee5dc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee5dc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee5dc-111">S_OK</span></span>|<span data-ttu-id="ee5dc-112">Строка появится в списке.</span><span class="sxs-lookup"><span data-stu-id="ee5dc-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="ee5dc-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ee5dc-113">S_FALSE</span></span>|<span data-ttu-id="ee5dc-114">Строка не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="ee5dc-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="ee5dc-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ee5dc-115">E_FAIL</span></span>|<span data-ttu-id="ee5dc-116">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ee5dc-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ee5dc-117">После того как метод возвращает E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ee5dc-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="ee5dc-118">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ee5dc-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee5dc-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ee5dc-119">Requirements</span></span>  
 <span data-ttu-id="ee5dc-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee5dc-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee5dc-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ee5dc-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee5dc-122">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee5dc-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee5dc-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee5dc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5dc-124">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="ee5dc-124">See also</span></span>

- [<span data-ttu-id="ee5dc-125">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="ee5dc-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="ee5dc-126">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="ee5dc-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ee5dc-127">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="ee5dc-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="ee5dc-128">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="ee5dc-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
