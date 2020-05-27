---
title: Метод IHostMemoryManager::CreateMAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 89c1d7b043d4369bf16a851924711c3c9d75791e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804530"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="401b7-102">Метод IHostMemoryManager::CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="401b7-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="401b7-103">Возвращает указатель интерфейса на экземпляр [IHostMAlloc](ihostmalloc-interface.md) , который используется для выполнения запросов на выделение из кучи, созданной узлом.</span><span class="sxs-lookup"><span data-stu-id="401b7-103">Gets an interface pointer to an [IHostMAlloc](ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401b7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="401b7-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="401b7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="401b7-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="401b7-106">окне Сочетание флагов [MALLOC_TYPE](malloc-type-enumeration.md) , определяющих характеристики выделяемой памяти.</span><span class="sxs-lookup"><span data-stu-id="401b7-106">[in] A combination of [MALLOC_TYPE](malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="401b7-107">заполняет Указатель на адрес `IHostMAlloc` экземпляра, предоставленного узлом.</span><span class="sxs-lookup"><span data-stu-id="401b7-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="401b7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="401b7-108">Return Value</span></span>  
  
|<span data-ttu-id="401b7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="401b7-109">HRESULT</span></span>|<span data-ttu-id="401b7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="401b7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="401b7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="401b7-111">S_OK</span></span>|<span data-ttu-id="401b7-112">`CreateMAlloc`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="401b7-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="401b7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="401b7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="401b7-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="401b7-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="401b7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="401b7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="401b7-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="401b7-116">The call timed out.</span></span>|  
|<span data-ttu-id="401b7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="401b7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="401b7-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="401b7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="401b7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="401b7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="401b7-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="401b7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="401b7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="401b7-121">E_FAIL</span></span>|<span data-ttu-id="401b7-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="401b7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="401b7-123">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="401b7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="401b7-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="401b7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="401b7-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="401b7-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="401b7-126">Недостаточно физической памяти для завершения запроса на выделение.</span><span class="sxs-lookup"><span data-stu-id="401b7-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="401b7-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="401b7-127">Remarks</span></span>  
 <span data-ttu-id="401b7-128">`CreateMAlloc`Возвращает объект, позволяющий среде CLR выполнять запросы на выделение через основное приложение, а не использовать стандартные функции Win32.</span><span class="sxs-lookup"><span data-stu-id="401b7-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="401b7-129">Требования</span><span class="sxs-lookup"><span data-stu-id="401b7-129">Requirements</span></span>  
 <span data-ttu-id="401b7-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="401b7-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="401b7-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="401b7-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="401b7-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="401b7-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="401b7-133">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="401b7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401b7-134">См. также статью</span><span class="sxs-lookup"><span data-stu-id="401b7-134">See also</span></span>

- [<span data-ttu-id="401b7-135">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="401b7-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
- [<span data-ttu-id="401b7-136">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="401b7-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
