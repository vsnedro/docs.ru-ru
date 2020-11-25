---
title: Метод ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
ms.openlocfilehash: cfc384a71ac7e91181bdec09f0d385bacbe31753
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716672"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="46887-102">Метод ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="46887-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>

<span data-ttu-id="46887-103">Возвращает указатель интерфейса на экземпляр [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) из заданного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="46887-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46887-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46887-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46887-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46887-105">Parameters</span></span>  

 `ppwzAssemblyReferences`  
 <span data-ttu-id="46887-106">окне Массив строк с завершающим нулем в форме "имя, свойство = значение..." , задающих список частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="46887-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="46887-107">окне Количество элементов в `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="46887-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="46887-108">заполняет Указатель интерфейса на `ICLRAssemblyReferenceList` объект, содержащий данные удостоверения сборки для списка сборок, указанных в параметре `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="46887-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46887-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46887-109">Return Value</span></span>  
  
|<span data-ttu-id="46887-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46887-110">HRESULT</span></span>|<span data-ttu-id="46887-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="46887-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46887-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="46887-112">S_OK</span></span>|<span data-ttu-id="46887-113">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="46887-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="46887-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="46887-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="46887-115">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="46887-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="46887-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="46887-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="46887-117">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="46887-117">The call timed out.</span></span>|  
|<span data-ttu-id="46887-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="46887-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="46887-119">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="46887-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="46887-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="46887-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="46887-121">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="46887-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="46887-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46887-122">E_FAIL</span></span>|<span data-ttu-id="46887-123">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="46887-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="46887-124">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="46887-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="46887-125">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="46887-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="46887-126">Требования</span><span class="sxs-lookup"><span data-stu-id="46887-126">Requirements</span></span>  

 <span data-ttu-id="46887-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46887-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46887-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="46887-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46887-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46887-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46887-130">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46887-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46887-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="46887-131">See also</span></span>

- [<span data-ttu-id="46887-132">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="46887-132">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="46887-133">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="46887-133">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
