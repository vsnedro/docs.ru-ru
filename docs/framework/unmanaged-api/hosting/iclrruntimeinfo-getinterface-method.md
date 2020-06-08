---
title: Метод ICLRRuntimeInfo::GetInterface
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
ms.openlocfilehash: 9cf9d48bf50ffc1fc56270c13215acfef6d9c3af
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504060"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="b5fc4-102">Метод ICLRRuntimeInfo::GetInterface</span><span class="sxs-lookup"><span data-stu-id="b5fc4-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="b5fc4-103">Загружает среду CLR в текущий процесс и возвращает указатели на интерфейсы среды выполнения, такие как [ICLRRuntimeHost](iclrruntimehost-interface.md), [метод iclrstrongname](iclrstrongname-interface.md)и [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b5fc4-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md), and [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="b5fc4-104">Этот метод заменяет все `CorBindTo` функции \* в разделе [устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="b5fc4-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5fc4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5fc4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5fc4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5fc4-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="b5fc4-107">окне Интерфейс CLSID для компонентного класса.</span><span class="sxs-lookup"><span data-stu-id="b5fc4-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="b5fc4-108">окне IID запрашиваемого `rclsid` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b5fc4-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="b5fc4-109">заполняет Указатель на запрашиваемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b5fc4-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5fc4-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b5fc4-110">Return Value</span></span>  
 <span data-ttu-id="b5fc4-111">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="b5fc4-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b5fc4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5fc4-112">HRESULT</span></span>|<span data-ttu-id="b5fc4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b5fc4-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5fc4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5fc4-114">S_OK</span></span>|<span data-ttu-id="b5fc4-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="b5fc4-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="b5fc4-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b5fc4-116">E_POINTER</span></span>|<span data-ttu-id="b5fc4-117">Параметр `ppUnk` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b5fc4-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="b5fc4-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b5fc4-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b5fc4-119">Недостаточно памяти для выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="b5fc4-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="b5fc4-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="b5fc4-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="b5fc4-121">Другая среда выполнения уже привязана к устаревшей политике активации CLR версии 2.</span><span class="sxs-lookup"><span data-stu-id="b5fc4-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5fc4-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5fc4-122">Remarks</span></span>  
 <span data-ttu-id="b5fc4-123">Этот метод приводит к тому, что среда CLR загружается, но не инициализируется.</span><span class="sxs-lookup"><span data-stu-id="b5fc4-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="b5fc4-124">В следующей таблице приведены поддерживаемые сочетания для `rclsid` и `riid` .</span><span class="sxs-lookup"><span data-stu-id="b5fc4-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="b5fc4-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="b5fc4-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="b5fc4-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="b5fc4-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="b5fc4-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="b5fc4-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="b5fc4-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="b5fc4-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="b5fc4-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b5fc4-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="b5fc4-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b5fc4-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="b5fc4-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b5fc4-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="b5fc4-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b5fc4-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="b5fc4-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="b5fc4-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="b5fc4-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="b5fc4-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="b5fc4-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="b5fc4-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="b5fc4-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="b5fc4-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="b5fc4-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b5fc4-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="b5fc4-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b5fc4-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5fc4-139">Требования</span><span class="sxs-lookup"><span data-stu-id="b5fc4-139">Requirements</span></span>  
 <span data-ttu-id="b5fc4-140">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5fc4-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5fc4-141">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="b5fc4-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b5fc4-142">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b5fc4-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5fc4-143">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5fc4-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5fc4-144">См. также</span><span class="sxs-lookup"><span data-stu-id="b5fc4-144">See also</span></span>

- [<span data-ttu-id="b5fc4-145">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="b5fc4-145">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="b5fc4-146">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b5fc4-146">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b5fc4-147">Размещение</span><span class="sxs-lookup"><span data-stu-id="b5fc4-147">Hosting</span></span>](index.md)
