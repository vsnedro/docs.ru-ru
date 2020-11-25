---
title: Метод ICLRMetaHost::GetRuntime
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
ms.openlocfilehash: 093fa64a7d51e0c2fdc304d2bb4f1c9f7b03e2ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730413"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="147cc-102">Метод ICLRMetaHost::GetRuntime</span><span class="sxs-lookup"><span data-stu-id="147cc-102">ICLRMetaHost::GetRuntime Method</span></span>

<span data-ttu-id="147cc-103">Возвращает интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , соответствующий определенной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="147cc-103">Gets the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="147cc-104">Этот метод заменяет функцию [CorBindToRuntimeEx](corbindtoruntimeex-function.md) , используемую с флагом [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="147cc-104">This method supersedes the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="147cc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="147cc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="147cc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="147cc-106">Parameters</span></span>  

 `pwzVersion`  
 <span data-ttu-id="147cc-107">окне Версия компиляции .NET Framework, хранящаяся в метаданных, в формате "v *A*. *B*[.*X*] ".</span><span class="sxs-lookup"><span data-stu-id="147cc-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v *A*.*B*[.*X*]".</span></span> <span data-ttu-id="147cc-108">*A*, *B* и *X* — это десятичные числа, соответствующие основной версии, дополнительной версии и номеру сборки.</span><span class="sxs-lookup"><span data-stu-id="147cc-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="147cc-109">Этот параметр должен соответствовать имени каталога для .NET Framework версии, так как она отображается в разделе К:\виндовс\микрософт.нет\фрамеворк или C:\Windows\Microsoft.NET\Framework64.</span><span class="sxs-lookup"><span data-stu-id="147cc-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="147cc-110">Примеры значений: "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" и "v 4.0. *X*", где *X* зависит от установленного номера сборки.</span><span class="sxs-lookup"><span data-stu-id="147cc-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="147cc-111">Требуется префикс "v".</span><span class="sxs-lookup"><span data-stu-id="147cc-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="147cc-112">окне Идентификатор требуемого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="147cc-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="147cc-113">В настоящее время единственным допустимым значением для этого параметра является IID_ICLRRuntimeInfo.</span><span class="sxs-lookup"><span data-stu-id="147cc-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="147cc-114">заполняет Указатель на интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , соответствующий запрошенной среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="147cc-114">[out] A pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="147cc-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="147cc-115">Return Value</span></span>  

 <span data-ttu-id="147cc-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="147cc-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="147cc-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="147cc-117">HRESULT</span></span>|<span data-ttu-id="147cc-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="147cc-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="147cc-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="147cc-119">S_OK</span></span>|<span data-ttu-id="147cc-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="147cc-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="147cc-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="147cc-121">E_POINTER</span></span>|<span data-ttu-id="147cc-122">`pwzVersion` или `ppRuntime` равно null.</span><span class="sxs-lookup"><span data-stu-id="147cc-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="147cc-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="147cc-123">Remarks</span></span>  

 <span data-ttu-id="147cc-124">Этот метод взаимодействует согласованно с устаревшими интерфейсами, такими как интерфейс [ICorRuntimeHost](icorruntimehost-interface.md) , и устаревшими функциями, такими как устаревшие `CorBindTo*` функции (см. статью [устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md) в API размещения .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="147cc-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="147cc-125">То есть среды выполнения, загруженные с помощью API прежних версий, видимы для нового API, а среды выполнения, которые загружаются с новым API, видимы для API прежних версий.</span><span class="sxs-lookup"><span data-stu-id="147cc-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="147cc-126">Требования</span><span class="sxs-lookup"><span data-stu-id="147cc-126">Requirements</span></span>  

 <span data-ttu-id="147cc-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="147cc-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="147cc-128">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="147cc-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="147cc-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="147cc-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="147cc-130">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="147cc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="147cc-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="147cc-131">See also</span></span>

- [<span data-ttu-id="147cc-132">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="147cc-132">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="147cc-133">Устаревшие интерфейсы размещения CLR и CoClasses</span><span class="sxs-lookup"><span data-stu-id="147cc-133">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="147cc-134">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="147cc-134">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="147cc-135">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="147cc-135">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="147cc-136">Размещение</span><span class="sxs-lookup"><span data-stu-id="147cc-136">Hosting</span></span>](index.md)
