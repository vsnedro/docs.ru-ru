---
title: Метод ICLRMetaHost::QueryLegacyV2RuntimeBinding
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
ms.openlocfilehash: d65191e515db9c302cef669a824ffd08327faf34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713994"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="96f3d-102">Метод ICLRMetaHost::QueryLegacyV2RuntimeBinding</span><span class="sxs-lookup"><span data-stu-id="96f3d-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>

<span data-ttu-id="96f3d-103">Возвращает интерфейс, представляющий среду выполнения, к которой привязана политика устаревшей активации, например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибута в записи файла конфигурации [ \<startup> элемента](../../configure-apps/file-schema/startup/startup-element.md) , путем непосредственного использования устаревших API-интерфейсов активации или путем вызова метода [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .</span><span class="sxs-lookup"><span data-stu-id="96f3d-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96f3d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96f3d-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96f3d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96f3d-105">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="96f3d-106">окне Обязательно. в настоящее время единственным допустимым значением для этого параметра является `IID_ICLRRuntimeInfo` .</span><span class="sxs-lookup"><span data-stu-id="96f3d-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="96f3d-107">[out] Обязательный.</span><span class="sxs-lookup"><span data-stu-id="96f3d-107">[out] Required.</span></span> <span data-ttu-id="96f3d-108">При возврате из этого метода содержит указатель на интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , представляющий среду выполнения, привязанную к устаревшей политике активации.</span><span class="sxs-lookup"><span data-stu-id="96f3d-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96f3d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="96f3d-109">Return Value</span></span>  

 <span data-ttu-id="96f3d-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="96f3d-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="96f3d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96f3d-111">HRESULT</span></span>|<span data-ttu-id="96f3d-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="96f3d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96f3d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="96f3d-113">S_OK</span></span>|<span data-ttu-id="96f3d-114">Метод успешно выполнен, и возвращена среда выполнения, которая была привязана к устаревшей политике активации.</span><span class="sxs-lookup"><span data-stu-id="96f3d-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="96f3d-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="96f3d-115">S_FALSE</span></span>|<span data-ttu-id="96f3d-116">Метод успешно выполнен, но устаревшая среда выполнения еще не привязана.</span><span class="sxs-lookup"><span data-stu-id="96f3d-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="96f3d-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="96f3d-117">E_NOINTERFACE</span></span>|<span data-ttu-id="96f3d-118">Метод обнаружил среду выполнения, которая была привязана к устаревшей политике активации, но параметр `riid` не поддерживается этой средой.</span><span class="sxs-lookup"><span data-stu-id="96f3d-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96f3d-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="96f3d-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96f3d-120">Требования</span><span class="sxs-lookup"><span data-stu-id="96f3d-120">Requirements</span></span>  

 <span data-ttu-id="96f3d-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96f3d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96f3d-122">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="96f3d-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="96f3d-123">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96f3d-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96f3d-124">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96f3d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96f3d-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="96f3d-125">See also</span></span>

- [<span data-ttu-id="96f3d-126">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="96f3d-126">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="96f3d-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="96f3d-127">Hosting</span></span>](index.md)
