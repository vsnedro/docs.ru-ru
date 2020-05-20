---
title: Метод ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
ms.openlocfilehash: 4f06dd7b85446eec986055418d2cf558b9b5bd7a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615934"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="34e98-102">Метод ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="34e98-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="34e98-103">Возвращает указатель на объект [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) , содержащий данные удостоверения сборки для сборок, на которые ссылается сборка в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="34e98-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34e98-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34e98-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34e98-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="34e98-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="34e98-106">окне Указатель интерфейса на объект, `IStream` содержащий сборку для оценки.</span><span class="sxs-lookup"><span data-stu-id="34e98-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="34e98-107">окне Предоставляется для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="34e98-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="34e98-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которое поддерживает Текущая версия среды CLR.</span><span class="sxs-lookup"><span data-stu-id="34e98-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="34e98-109">окне Указатель на объект [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , содержащий данные удостоверения сборки для исключаемых сборок `ppReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="34e98-109">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="34e98-110">заполняет Указатель на адрес `ICLRReferenceAssemblyEnum` объекта, который содержит данные идентификации сборки для сборок, на которые ссылается сборка в `pStream` , за исключением сборок в `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="34e98-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34e98-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="34e98-111">Return Value</span></span>  
  
|<span data-ttu-id="34e98-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34e98-112">HRESULT</span></span>|<span data-ttu-id="34e98-113">Описание</span><span class="sxs-lookup"><span data-stu-id="34e98-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34e98-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="34e98-114">S_OK</span></span>|<span data-ttu-id="34e98-115">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="34e98-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="34e98-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="34e98-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="34e98-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="34e98-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="34e98-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="34e98-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="34e98-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="34e98-119">The call timed out.</span></span>|  
|<span data-ttu-id="34e98-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="34e98-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="34e98-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="34e98-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="34e98-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="34e98-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="34e98-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="34e98-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="34e98-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="34e98-124">E_FAIL</span></span>|<span data-ttu-id="34e98-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="34e98-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="34e98-126">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="34e98-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="34e98-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="34e98-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34e98-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="34e98-128">Remarks</span></span>  
 <span data-ttu-id="34e98-129">Вызывающий объект может исключить набор известных ссылок на сборки из возвращенного списка.</span><span class="sxs-lookup"><span data-stu-id="34e98-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="34e98-130">Этот набор определяется `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="34e98-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34e98-131">Требования</span><span class="sxs-lookup"><span data-stu-id="34e98-131">Requirements</span></span>  
 <span data-ttu-id="34e98-132">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34e98-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34e98-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="34e98-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34e98-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="34e98-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34e98-135">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34e98-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34e98-136">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="34e98-136">See also</span></span>

- [<span data-ttu-id="34e98-137">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="34e98-137">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="34e98-138">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="34e98-138">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="34e98-139">Интерфейс ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="34e98-139">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
