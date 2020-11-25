---
title: Метод ICLRRuntimeInfo::IsLoaded
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: 66ae74deba9ceab9d1ea6b2c0b96a87bf44f32ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714930"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="dface-102">Метод ICLRRuntimeInfo::IsLoaded</span><span class="sxs-lookup"><span data-stu-id="dface-102">ICLRRuntimeInfo::IsLoaded Method</span></span>

<span data-ttu-id="dface-103">Указывает, загружается ли в процесс общеязыковая среда выполнения (CLR), связанная с интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="dface-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="dface-104">Среду выполнения можно загрузить без запуска.</span><span class="sxs-lookup"><span data-stu-id="dface-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dface-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dface-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dface-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dface-106">Parameters</span></span>  

 `hndProcess`  
 <span data-ttu-id="dface-107">окне Обработчик процесса.</span><span class="sxs-lookup"><span data-stu-id="dface-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="dface-108">[out] `true` значение, если среда CLR загружена в процесс; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="dface-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dface-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dface-109">Return Value</span></span>  

 <span data-ttu-id="dface-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="dface-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="dface-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dface-111">HRESULT</span></span>|<span data-ttu-id="dface-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="dface-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dface-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="dface-113">S_OK</span></span>|<span data-ttu-id="dface-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="dface-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="dface-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="dface-115">E_POINTER</span></span>|<span data-ttu-id="dface-116">Параметр `pbLoaded` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="dface-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dface-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="dface-117">Remarks</span></span>  

 <span data-ttu-id="dface-118">Этот метод обеспечивает обратную совместимость со следующими функциями и интерфейсами:</span><span class="sxs-lookup"><span data-stu-id="dface-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="dface-119">Интерфейс [ICorRuntimeHost](icorruntimehost-interface.md) (в API размещения .NET Framework версии 1).</span><span class="sxs-lookup"><span data-stu-id="dface-119">[ICorRuntimeHost](icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="dface-120">Интерфейс [ICLRRuntimeHost](iclrruntimehost-interface.md) (в API размещения .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="dface-120">[ICLRRuntimeHost](iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="dface-121">Устаревшие `CorBindTo*` функции (см. раздел [нерекомендуемые функции размещения CLR](deprecated-clr-hosting-functions.md) в API размещения .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="dface-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="dface-122">Узел может вызвать одну из устаревших `CorBindTo*` функций, например функцию [CorBindToRuntime](corbindtoruntime-function.md) , для создания экземпляра конкретной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="dface-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="dface-123">Затем узел может вызвать метод [ICLRMetaHost::-Runtime](iclrmetahost-getruntime-method.md) и указать тот же номер версии для получения интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="dface-123">The host could then call the [ICLRMetaHost::GetRuntime](iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="dface-124">Если узел затем вызывает `IsLoaded` метод для возвращенного интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , `pbLoaded` возвращает `true` ; в противном случае возвращается значение `false` .</span><span class="sxs-lookup"><span data-stu-id="dface-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dface-125">Требования</span><span class="sxs-lookup"><span data-stu-id="dface-125">Requirements</span></span>  

 <span data-ttu-id="dface-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dface-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dface-127">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="dface-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dface-128">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dface-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dface-129">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dface-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dface-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dface-130">See also</span></span>

- [<span data-ttu-id="dface-131">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="dface-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="dface-132">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="dface-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="dface-133">Размещение</span><span class="sxs-lookup"><span data-stu-id="dface-133">Hosting</span></span>](index.md)
