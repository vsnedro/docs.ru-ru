---
title: Метод ICLRMetaHostPolicy::GetRequestedRuntime
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy.GetRequestedRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type:
- apiref
ms.openlocfilehash: 52da5ec7ccd6ce48871e13a94f5957fa00d2a613
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703547"
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a><span data-ttu-id="56606-102">Метод ICLRMetaHostPolicy::GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="56606-102">ICLRMetaHostPolicy::GetRequestedRuntime Method</span></span>

<span data-ttu-id="56606-103">Предоставляет интерфейс для предпочитаемой версии общеязыковой среды выполнения (CLR) на основе политики размещения, управляемой сборки, строки версии и потока конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56606-103">Provides an interface to a preferred version of the common language runtime (CLR) based on a hosting policy, managed assembly, version string, and configuration stream.</span></span> <span data-ttu-id="56606-104">Этот метод не выполняет фактическую загрузку или активацию среды CLR, но просто возвращает интерфейс [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) , представляющий результат политики.</span><span class="sxs-lookup"><span data-stu-id="56606-104">This method does not actually load or activate the CLR, but simply returns the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents the policy result.</span></span> <span data-ttu-id="56606-105">Этот метод заменяет методы [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [жетрекуестедрунтимеверсион](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [корбиндторунтимехост](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [корбиндторунтимебикфг](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)и [жеткоррекуиредверсион](getcorrequiredversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="56606-105">This method supersedes the [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md), and [GetCORRequiredVersion](getcorrequiredversion-function.md) methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="56606-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56606-106">Syntax</span></span>

```cpp
HRESULT GetRequestedRuntime(
    [in]  METAHOST_POLICY_FLAGS dwPolicyFlags,
    [in]  LPCWSTR pwzBinary,
    [in]  IStream *pCfgStream,
    [in, out, size_is(*pcchVersion)] LPWSTR pwzVersion,
    [in, out]  DWORD *pcchVersion,
    [out, size_is(*pcchImageVersion)] LPWSTR pwzImageVersion,
    [in, out]  DWORD *pcchImageVersion,
    [out] DWORD *pdwConfigFlags,
    [in]  REFIID  riid
    [out, iid_is(riid), retval] LPVOID *ppRuntime);
```

## <a name="parameters"></a><span data-ttu-id="56606-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="56606-107">Parameters</span></span>

|<span data-ttu-id="56606-108">Имя</span><span class="sxs-lookup"><span data-stu-id="56606-108">Name</span></span>|<span data-ttu-id="56606-109">Описание</span><span class="sxs-lookup"><span data-stu-id="56606-109">Description</span></span>|
|----------|-----------------|
|`dwPolicyFlags`|<span data-ttu-id="56606-110">[in] Обязательный.</span><span class="sxs-lookup"><span data-stu-id="56606-110">[in] Required.</span></span> <span data-ttu-id="56606-111">Указывает элемент перечисления [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) , представляющий политику привязки, и любое количество модификаторов.</span><span class="sxs-lookup"><span data-stu-id="56606-111">Specifies a member of the [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) enumeration, representing a binding policy, and any number of modifiers.</span></span> <span data-ttu-id="56606-112">Единственной доступной в данный момент политикой является [METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="56606-112">The only policy that is currently available is [METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md).</span></span><br /><br /> <span data-ttu-id="56606-113">К модификаторам относятся [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md)и [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="56606-113">Modifiers include [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md), and [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md).</span></span>|
|`pwzBinary`|<span data-ttu-id="56606-114">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="56606-114">[in] Optional.</span></span> <span data-ttu-id="56606-115">Задает путь к файлу сборки.</span><span class="sxs-lookup"><span data-stu-id="56606-115">Specifies the assembly file path.</span></span>|
|`pCfgStream`|<span data-ttu-id="56606-116">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="56606-116">[in] Optional.</span></span> <span data-ttu-id="56606-117">Задает файл конфигурации в виде <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="56606-117">Specifies the configuration file as a <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.</span></span>|
|`pwzVersion`|<span data-ttu-id="56606-118">[in, out] Необязательный.</span><span class="sxs-lookup"><span data-stu-id="56606-118">[in, out] Optional.</span></span> <span data-ttu-id="56606-119">Задает или возвращает предпочтительную версию среды CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="56606-119">Specifies or returns the preferred CLR version to be loaded.</span></span>|
|`pcchVersion`|<span data-ttu-id="56606-120">[in, out] Обязательный.</span><span class="sxs-lookup"><span data-stu-id="56606-120">[in, out] Required.</span></span> <span data-ttu-id="56606-121">Указывает ожидаемый размер `pwzVersion` в качестве входных данных для предотвращения переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="56606-121">Specifies the expected size of `pwzVersion` as input, to avoid buffer overruns.</span></span> <span data-ttu-id="56606-122">Если `pwzVersion` имеет значение NULL, `pcchVersion` содержит ожидаемый размер `pwzVersion` при возвращении значения `GetRequestedRuntime`, чтобы разрешить предварительное выделение; в противном случае `pcchVersion` содержит число символов, записанных в `pwzVersion`.</span><span class="sxs-lookup"><span data-stu-id="56606-122">If `pwzVersion` is null, `pcchVersion` contains the expected size of `pwzVersion` when `GetRequestedRuntime` returns, to allow pre-allocation; otherwise, `pcchVersion` contains the number of characters written to `pwzVersion`.</span></span>|
|`pwzImageVersion`|<span data-ttu-id="56606-123">[out] Необязательный.</span><span class="sxs-lookup"><span data-stu-id="56606-123">[out] Optional.</span></span> <span data-ttu-id="56606-124">При `GetRequestedRuntime` возврате содержит версию среды CLR, соответствующую возвращаемому интерфейсу [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="56606-124">When `GetRequestedRuntime` returns, contains the CLR version corresponding to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that is returned.</span></span>|
|`pcchImageVersion`|<span data-ttu-id="56606-125">[in, out] Необязательный.</span><span class="sxs-lookup"><span data-stu-id="56606-125">[in, out] Optional.</span></span> <span data-ttu-id="56606-126">Указывает размер `pwzImageVersion` в качестве входных данных для предотвращения переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="56606-126">Specifies the size of `pwzImageVersion` as input to avoid buffer overruns.</span></span> <span data-ttu-id="56606-127">Если `pwzImageVersion` имеет значение NULL, `pcchImageVersion` содержит требуемый размер `pwzImageVersion` при возвращении значения `GetRequestedRuntime`, чтобы разрешить предварительное выделение.</span><span class="sxs-lookup"><span data-stu-id="56606-127">If `pwzImageVersion` is null, `pcchImageVersion` contains the required size of `pwzImageVersion` when `GetRequestedRuntime` returns, to allow pre-allocation.</span></span>|
|`pdwConfigFlags`|<span data-ttu-id="56606-128">[out] Необязательный.</span><span class="sxs-lookup"><span data-stu-id="56606-128">[out] Optional.</span></span> <span data-ttu-id="56606-129">Если в процессе `GetRequestedRuntime` привязки использует файл конфигурации, то при его возврате `pdwConfigFlags` содержит [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) значение, указывающее, установлен ли в элементе [ \< Startup>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) `useLegacyV2RuntimeActivationPolicy` набор атрибутов, и значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="56606-129">If `GetRequestedRuntime` uses a configuration file during the binding process, when it returns, `pdwConfigFlags` contains a [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) value that indicates whether the [\<startup>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) element has the `useLegacyV2RuntimeActivationPolicy` attribute set, and the value of the attribute.</span></span> <span data-ttu-id="56606-130">Примените маску [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md) к, чтобы `pdwConfigFlags` получить значения, относящиеся к `useLegacyV2RuntimeActivationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="56606-130">Apply the [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md) mask to `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|
|`riid`|<span data-ttu-id="56606-131">окне Указывает идентификатор интерфейса IID_ICLRRuntimeInfo для запрошенного интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="56606-131">[in] Specifies the interface identifier IID_ICLRRuntimeInfo for the requested [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>|
|`ppRuntime`|<span data-ttu-id="56606-132">заполняет При `GetRequestedRuntime` возврате содержит указатель на соответствующий интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="56606-132">[out] When `GetRequestedRuntime` returns, contains a pointer to the corresponding [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>|

## <a name="remarks"></a><span data-ttu-id="56606-133">Комментарии</span><span class="sxs-lookup"><span data-stu-id="56606-133">Remarks</span></span>

<span data-ttu-id="56606-134">После успешного завершения этого метода имеет место его побочный эффект в виде объединения дополнительных флагов с текущими флагами запуска по умолчанию из возвращенного интерфейса среды выполнения тогда и только тогда, когда один или несколько из следующих элементов существуют в потоке конфигурации в разделе `<configuration><runtime>`.</span><span class="sxs-lookup"><span data-stu-id="56606-134">When this method succeeds, it has the side effect of combining additional flags with the current default startup flags of the returned runtime interface, if and only if one or more of the following elements exist in the configuration stream within the `<configuration><runtime>` section:</span></span>

- <span data-ttu-id="56606-135">`<gcServer enabled="true"/>` приводит к заданию `STARTUP_SERVER_GC`.</span><span class="sxs-lookup"><span data-stu-id="56606-135">`<gcServer enabled="true"/>` causes `STARTUP_SERVER_GC` to be set.</span></span>

- <span data-ttu-id="56606-136">`<etwEnable enabled="true"/>` приводит к заданию `STARTUP_ETW`.</span><span class="sxs-lookup"><span data-stu-id="56606-136">`<etwEnable enabled="true"/>` causes `STARTUP_ETW` to be set.</span></span>

- <span data-ttu-id="56606-137">`<appDomainResourceMonitoring enabled="true"/>` приводит к заданию `STARTUP_ARM`.</span><span class="sxs-lookup"><span data-stu-id="56606-137">`<appDomainResourceMonitoring enabled="true"/>` causes `STARTUP_ARM` to be set.</span></span>

<span data-ttu-id="56606-138">По умолчанию результирующее значение`STARTUP_FLAGS` является побитовым или сочетанием заданных значений из предыдущего списка с флагами запуска по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="56606-138">The resulting default `STARTUP_FLAGS` value is the bitwise OR combination of the values that are set from the preceding list with the default startup flags.</span></span>

## <a name="return-value"></a><span data-ttu-id="56606-139">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="56606-139">Return Value</span></span>

<span data-ttu-id="56606-140">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="56606-140">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>

|<span data-ttu-id="56606-141">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56606-141">HRESULT</span></span>|<span data-ttu-id="56606-142">Описание</span><span class="sxs-lookup"><span data-stu-id="56606-142">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="56606-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="56606-143">S_OK</span></span>|<span data-ttu-id="56606-144">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="56606-144">The method completed successfully.</span></span>|
|<span data-ttu-id="56606-145">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="56606-145">E_POINTER</span></span>|<span data-ttu-id="56606-146">`pwzVersion` не равен NULL, а `pcchVersion` равен NULL.</span><span class="sxs-lookup"><span data-stu-id="56606-146">`pwzVersion` is not null and `pcchVersion` is null.</span></span><br /><br /> <span data-ttu-id="56606-147">-или-</span><span class="sxs-lookup"><span data-stu-id="56606-147">-or-</span></span><br /><br /> <span data-ttu-id="56606-148">`pwzImageVersion` не равен NULL, а `pcchImageVersion` равен NULL.</span><span class="sxs-lookup"><span data-stu-id="56606-148">`pwzImageVersion` is not null and `pcchImageVersion` is null.</span></span>|
|<span data-ttu-id="56606-149">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="56606-149">E_INVALIDARG</span></span>|<span data-ttu-id="56606-150">`dwPolicyFlags` не указывает `METAHOST_POLICY_HIGHCOMPAT`.</span><span class="sxs-lookup"><span data-stu-id="56606-150">`dwPolicyFlags` does not specify `METAHOST_POLICY_HIGHCOMPAT`.</span></span>|
|<span data-ttu-id="56606-151">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="56606-151">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="56606-152">Памяти, выделенной для `pwzVersion`, недостаточно.</span><span class="sxs-lookup"><span data-stu-id="56606-152">The memory allocated to `pwzVersion` is inadequate.</span></span><br /><br /> <span data-ttu-id="56606-153">-или-</span><span class="sxs-lookup"><span data-stu-id="56606-153">-or-</span></span><br /><br /> <span data-ttu-id="56606-154">Памяти, выделенной для `pwzImageVersion`, недостаточно.</span><span class="sxs-lookup"><span data-stu-id="56606-154">The memory allocated to `pwzImageVersion` is inadequate.</span></span>|
|<span data-ttu-id="56606-155">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="56606-155">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="56606-156">`dwPolicyFlags` включает в себя METAHOST_POLICY_APPLY_UPGRADE_POLICY, а как `pwzVersion`, так и `pcchVersion` имеют значение NULL.</span><span class="sxs-lookup"><span data-stu-id="56606-156">`dwPolicyFlags` includes METAHOST_POLICY_APPLY_UPGRADE_POLICY, and both `pwzVersion` and `pcchVersion` are null.</span></span>|

## <a name="requirements"></a><span data-ttu-id="56606-157">Требования</span><span class="sxs-lookup"><span data-stu-id="56606-157">Requirements</span></span>

<span data-ttu-id="56606-158">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56606-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="56606-159">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="56606-159">**Header:** MetaHost.h</span></span>

<span data-ttu-id="56606-160">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="56606-160">**Library:** Included as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="56606-161">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56606-161">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="56606-162">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="56606-162">See also</span></span>

- [<span data-ttu-id="56606-163">Интерфейс ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="56606-163">ICLRMetaHostPolicy Interface</span></span>](iclrmetahostpolicy-interface.md)
- [<span data-ttu-id="56606-164">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="56606-164">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="56606-165">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="56606-165">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="56606-166">Размещение</span><span class="sxs-lookup"><span data-stu-id="56606-166">Hosting</span></span>](index.md)
