---
title: Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
ms.openlocfilehash: abba19600616cad8ba3377ae2ebb23459449d2a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615986"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="4cfee-102">Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="4cfee-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="4cfee-103">Возвращает канонические данные удостоверений сборки для сборки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="4cfee-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cfee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4cfee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cfee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4cfee-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="4cfee-106">окне Оцениваемый поток сборки.</span><span class="sxs-lookup"><span data-stu-id="4cfee-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4cfee-107">окне Предоставляется для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="4cfee-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="4cfee-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которое поддерживает Текущая версия среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4cfee-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="4cfee-109">заполняет Буфер, содержащий непрозрачные данные идентификации сборки.</span><span class="sxs-lookup"><span data-stu-id="4cfee-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="4cfee-110">[вход, выход] Размер `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="4cfee-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cfee-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4cfee-111">Return Value</span></span>  
  
|<span data-ttu-id="4cfee-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cfee-112">HRESULT</span></span>|<span data-ttu-id="4cfee-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4cfee-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cfee-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cfee-114">S_OK</span></span>|<span data-ttu-id="4cfee-115">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="4cfee-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="4cfee-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4cfee-116">E_INVALIDARG</span></span>|<span data-ttu-id="4cfee-117">Переданный параметр `pStream` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="4cfee-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="4cfee-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4cfee-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4cfee-119">Размер `pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="4cfee-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="4cfee-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4cfee-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4cfee-121">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4cfee-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4cfee-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4cfee-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4cfee-123">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="4cfee-123">The call timed out.</span></span>|  
|<span data-ttu-id="4cfee-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4cfee-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4cfee-125">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="4cfee-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4cfee-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4cfee-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4cfee-127">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="4cfee-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4cfee-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cfee-128">E_FAIL</span></span>|<span data-ttu-id="4cfee-129">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4cfee-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4cfee-130">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4cfee-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4cfee-131">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4cfee-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cfee-132">Требования</span><span class="sxs-lookup"><span data-stu-id="4cfee-132">Requirements</span></span>  
 <span data-ttu-id="4cfee-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cfee-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cfee-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4cfee-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cfee-135">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4cfee-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cfee-136">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cfee-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfee-137">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4cfee-137">See also</span></span>

- [<span data-ttu-id="4cfee-138">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="4cfee-138">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4cfee-139">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="4cfee-139">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
