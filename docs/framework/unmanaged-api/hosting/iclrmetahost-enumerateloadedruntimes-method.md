---
title: Метод ICLRMetaHost::EnumerateLoadedRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: 2e22b8a2d0213b3bd766d80218d6f396721a90e1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703766"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="b4bbd-102">Метод ICLRMetaHost::EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="b4bbd-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="b4bbd-103">Возвращает перечисление, содержащее допустимый указатель интерфейса [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) для каждой версии среды CLR, загруженной в заданный процесс.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="b4bbd-104">Этот метод заменяет функцию [GetVersionFromProcess](getversionfromprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b4bbd-104">This method supersedes the [GetVersionFromProcess](getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4bbd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4bbd-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4bbd-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4bbd-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="b4bbd-107">окне Описатель процесса для проверки загруженных сред выполнения.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="b4bbd-108">заполняет <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>Перечисление интерфейсов [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , соответствующих каждой среде CLR, загруженной процессом.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4bbd-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b4bbd-109">Return Value</span></span>  
 <span data-ttu-id="b4bbd-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b4bbd-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4bbd-111">HRESULT</span></span>|<span data-ttu-id="b4bbd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b4bbd-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4bbd-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4bbd-113">S_OK</span></span>|<span data-ttu-id="b4bbd-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b4bbd-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b4bbd-115">E_POINTER</span></span>|<span data-ttu-id="b4bbd-116">Параметр `ppEnumerator` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b4bbd-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4bbd-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b4bbd-117">Remarks</span></span>  
 <span data-ttu-id="b4bbd-118">Этот метод перечисляет все загруженные среды выполнения, даже если они были загружены с устаревшими функциями, такими как [CorBindToRuntime](corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="b4bbd-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4bbd-119">Требования</span><span class="sxs-lookup"><span data-stu-id="b4bbd-119">Requirements</span></span>  
 <span data-ttu-id="b4bbd-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4bbd-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4bbd-121">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="b4bbd-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b4bbd-122">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b4bbd-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4bbd-123">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4bbd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4bbd-124">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b4bbd-124">See also</span></span>

- [<span data-ttu-id="b4bbd-125">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="b4bbd-125">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="b4bbd-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="b4bbd-126">Hosting</span></span>](index.md)
