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
ms.openlocfilehash: 7b09bb9c3abcb23997bfd412c3ea939404e583c1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504177"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="e0989-102">Метод ICLRMetaHost::EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="e0989-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="e0989-103">Возвращает перечисление, содержащее допустимый указатель интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) для каждой версии среды CLR, загруженной в заданный процесс.</span><span class="sxs-lookup"><span data-stu-id="e0989-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="e0989-104">Этот метод заменяет функцию [GetVersionFromProcess](getversionfromprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e0989-104">This method supersedes the [GetVersionFromProcess](getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0989-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0989-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0989-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0989-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="e0989-107">окне Описатель процесса для проверки загруженных сред выполнения.</span><span class="sxs-lookup"><span data-stu-id="e0989-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="e0989-108">заполняет <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>Перечисление интерфейсов [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , соответствующих каждой среде CLR, загруженной процессом.</span><span class="sxs-lookup"><span data-stu-id="e0989-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0989-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e0989-109">Return Value</span></span>  
 <span data-ttu-id="e0989-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="e0989-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e0989-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0989-111">HRESULT</span></span>|<span data-ttu-id="e0989-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e0989-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0989-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0989-113">S_OK</span></span>|<span data-ttu-id="e0989-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e0989-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="e0989-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e0989-115">E_POINTER</span></span>|<span data-ttu-id="e0989-116">Параметр `ppEnumerator` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e0989-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0989-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0989-117">Remarks</span></span>  
 <span data-ttu-id="e0989-118">Этот метод перечисляет все загруженные среды выполнения, даже если они были загружены с устаревшими функциями, такими как [CorBindToRuntime](corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="e0989-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0989-119">Требования</span><span class="sxs-lookup"><span data-stu-id="e0989-119">Requirements</span></span>  
 <span data-ttu-id="e0989-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0989-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0989-121">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="e0989-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e0989-122">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e0989-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0989-123">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0989-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0989-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e0989-124">See also</span></span>

- [<span data-ttu-id="e0989-125">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="e0989-125">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="e0989-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="e0989-126">Hosting</span></span>](index.md)
