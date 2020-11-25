---
title: Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
ms.openlocfilehash: 443acfa77dc8103008263f19bed116d02e7ea676
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716748"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="f76b5-102">Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="f76b5-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>

<span data-ttu-id="f76b5-103">Возвращает данные привязки удостоверения сборки для сборки по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="f76b5-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f76b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f76b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f76b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f76b5-105">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="f76b5-106">окне Путь к файлу, который необходимо вычислить.</span><span class="sxs-lookup"><span data-stu-id="f76b5-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f76b5-107">окне Значение перечисления [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) , указывающее тип удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="f76b5-107">[in] A value of the [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="f76b5-108">Предоставляется для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="f76b5-108">Provided for future extensibility.</span></span> <span data-ttu-id="f76b5-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT — единственное значение, поддерживаемое общеязыковой средой выполнения (CLR) версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="f76b5-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="f76b5-110">заполняет Буфер, содержащий непрозрачные данные идентификации сборки.</span><span class="sxs-lookup"><span data-stu-id="f76b5-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="f76b5-111">[вход, выход] Указатель на размер `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="f76b5-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f76b5-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f76b5-112">Return Value</span></span>  
  
|<span data-ttu-id="f76b5-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f76b5-113">HRESULT</span></span>|<span data-ttu-id="f76b5-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="f76b5-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f76b5-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f76b5-115">S_OK</span></span>|<span data-ttu-id="f76b5-116">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="f76b5-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="f76b5-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f76b5-117">E_INVALIDARG</span></span>|<span data-ttu-id="f76b5-118">Переданный параметр `pwzFilePath` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="f76b5-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="f76b5-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f76b5-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f76b5-120">Размер `pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="f76b5-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="f76b5-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f76b5-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f76b5-122">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f76b5-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f76b5-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f76b5-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f76b5-124">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f76b5-124">The call timed out.</span></span>|  
|<span data-ttu-id="f76b5-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f76b5-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f76b5-126">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f76b5-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f76b5-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f76b5-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f76b5-128">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f76b5-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f76b5-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f76b5-129">E_FAIL</span></span>|<span data-ttu-id="f76b5-130">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f76b5-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f76b5-131">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f76b5-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f76b5-132">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f76b5-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f76b5-133">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f76b5-133">Remarks</span></span>  

 <span data-ttu-id="f76b5-134">`GetBindingIdentityFromFile` обычно вызывается дважды.</span><span class="sxs-lookup"><span data-stu-id="f76b5-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="f76b5-135">Первый вызов предоставляет значение NULL для `pwzBuffer` , а метод возвращает соответствующий размер в `pcchBufferSize` .</span><span class="sxs-lookup"><span data-stu-id="f76b5-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="f76b5-136">Второй вызов предоставляет соответствующий буфер, а метод возвращает фактические данные буфера после завершения.</span><span class="sxs-lookup"><span data-stu-id="f76b5-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f76b5-137">Требования</span><span class="sxs-lookup"><span data-stu-id="f76b5-137">Requirements</span></span>  

 <span data-ttu-id="f76b5-138">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f76b5-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f76b5-139">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f76b5-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f76b5-140">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f76b5-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f76b5-141">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f76b5-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f76b5-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f76b5-142">See also</span></span>

- [<span data-ttu-id="f76b5-143">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="f76b5-143">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f76b5-144">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="f76b5-144">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f76b5-145">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f76b5-145">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
