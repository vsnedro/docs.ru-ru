---
title: Метод ICLRAppDomainResourceMonitor::GetCurrentAllocated
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
ms.openlocfilehash: 685d303b31b8f8c20cbbdb8aec6fc127650aa32a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616051"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="bc99c-102">Метод ICLRAppDomainResourceMonitor::GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="bc99c-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="bc99c-103">Возвращает общий размер (в байтах) всех выделений памяти, сделанных доменом приложения с момента его создания, без вычитания памяти, которая была собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="bc99c-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc99c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc99c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc99c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc99c-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="bc99c-106">окне ИДЕНТИФИКАТОР запрошенного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="bc99c-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="bc99c-107">заполняет Указатель на общий размер всех выделений памяти.</span><span class="sxs-lookup"><span data-stu-id="bc99c-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc99c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bc99c-108">Return Value</span></span>  
 <span data-ttu-id="bc99c-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="bc99c-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bc99c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc99c-110">HRESULT</span></span>|<span data-ttu-id="bc99c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="bc99c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc99c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc99c-112">S_OK</span></span>|<span data-ttu-id="bc99c-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="bc99c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="bc99c-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="bc99c-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="bc99c-115">Домен приложения был выгружен или не существует.</span><span class="sxs-lookup"><span data-stu-id="bc99c-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc99c-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="bc99c-116">Remarks</span></span>  
 <span data-ttu-id="bc99c-117">Этот метод является неуправляемым эквивалентом управляемого <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> Свойства.</span><span class="sxs-lookup"><span data-stu-id="bc99c-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc99c-118">Требования</span><span class="sxs-lookup"><span data-stu-id="bc99c-118">Requirements</span></span>  
 <span data-ttu-id="bc99c-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc99c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc99c-120">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="bc99c-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bc99c-121">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bc99c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc99c-122">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc99c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc99c-123">См. также статью</span><span class="sxs-lookup"><span data-stu-id="bc99c-123">See also</span></span>

- [<span data-ttu-id="bc99c-124">Интерфейс ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="bc99c-124">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="bc99c-125">Мониторинг ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="bc99c-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="bc99c-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="bc99c-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="bc99c-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="bc99c-127">Hosting</span></span>](index.md)
