---
title: Метод ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
ms.openlocfilehash: 98af9931e219c384b017d3c70fe21cdb6e052ac1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615960"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="54a0a-102">Метод ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="54a0a-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="54a0a-103">Возвращает перечислитель [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) для удостоверений сборок, на которые ссылается сборка с указанным типом удостоверения.</span><span class="sxs-lookup"><span data-stu-id="54a0a-103">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54a0a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54a0a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54a0a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="54a0a-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="54a0a-106">окне Допустимое значение, указывающее архитектуру процессора, как определено в WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="54a0a-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="54a0a-107">окне Предоставляется для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="54a0a-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="54a0a-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которое поддерживает Текущая версия среды CLR.</span><span class="sxs-lookup"><span data-stu-id="54a0a-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="54a0a-109">окне Идентификатор привязки непрозрачной сборки, обычно возвращаемый из вызова метода [ICLRAssemblyIdentityManager:: GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) или [ICLRAssemblyIdentityManager:: жетбиндингидентитифромстреам](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) .</span><span class="sxs-lookup"><span data-stu-id="54a0a-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="54a0a-110">заполняет Указатель интерфейса на `ICLRProbingAssemblyEnum` перечислитель, содержащий ссылки на сборки, на которые ссылается сборка, определенная параметром `pwzReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="54a0a-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54a0a-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="54a0a-111">Return Value</span></span>  
  
|<span data-ttu-id="54a0a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="54a0a-112">HRESULT</span></span>|<span data-ttu-id="54a0a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="54a0a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54a0a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="54a0a-114">S_OK</span></span>|<span data-ttu-id="54a0a-115">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="54a0a-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="54a0a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="54a0a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="54a0a-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="54a0a-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="54a0a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="54a0a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="54a0a-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="54a0a-119">The call timed out.</span></span>|  
|<span data-ttu-id="54a0a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="54a0a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="54a0a-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="54a0a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="54a0a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="54a0a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="54a0a-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="54a0a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="54a0a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="54a0a-124">E_FAIL</span></span>|<span data-ttu-id="54a0a-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="54a0a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="54a0a-126">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="54a0a-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="54a0a-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="54a0a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54a0a-128">Требования</span><span class="sxs-lookup"><span data-stu-id="54a0a-128">Requirements</span></span>  
 <span data-ttu-id="54a0a-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54a0a-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54a0a-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="54a0a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54a0a-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="54a0a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54a0a-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54a0a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54a0a-133">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="54a0a-133">See also</span></span>

- [<span data-ttu-id="54a0a-134">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="54a0a-134">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="54a0a-135">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="54a0a-135">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="54a0a-136">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="54a0a-136">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
