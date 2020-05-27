---
title: Метод IHostMAlloc::Free
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
ms.openlocfilehash: 1dd5ed4c556a5a4d4425a9c0730cebf22ff1785b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804625"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="d8ca9-102">Метод IHostMAlloc::Free</span><span class="sxs-lookup"><span data-stu-id="d8ca9-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="d8ca9-103">Освобождает память, выделенную с помощью функции [Alloc](ihostmalloc-alloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d8ca9-103">Frees memory that was allocated by using the [Alloc](ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ca9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8ca9-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8ca9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8ca9-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="d8ca9-106">окне Указатель на память, которую необходимо освободить.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8ca9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d8ca9-107">Return Value</span></span>  
  
|<span data-ttu-id="d8ca9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8ca9-108">HRESULT</span></span>|<span data-ttu-id="d8ca9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d8ca9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8ca9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8ca9-110">S_OK</span></span>|<span data-ttu-id="d8ca9-111">`Free`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="d8ca9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d8ca9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d8ca9-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d8ca9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d8ca9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d8ca9-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-115">The call timed out.</span></span>|  
|<span data-ttu-id="d8ca9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8ca9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d8ca9-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d8ca9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d8ca9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d8ca9-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d8ca9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8ca9-120">E_FAIL</span></span>|<span data-ttu-id="d8ca9-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d8ca9-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d8ca9-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d8ca9-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="d8ca9-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="d8ca9-125">Предпринята попытка освободить память, которая не была выделена через узел.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8ca9-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="d8ca9-126">Remarks</span></span>  
 <span data-ttu-id="d8ca9-127">Если `pMem` параметр ссылается на область памяти, которая не была выделена с помощью вызова `Alloc` , узел должен возвращать HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="d8ca9-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8ca9-128">Требования</span><span class="sxs-lookup"><span data-stu-id="d8ca9-128">Requirements</span></span>  
 <span data-ttu-id="d8ca9-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8ca9-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d8ca9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8ca9-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d8ca9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8ca9-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8ca9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ca9-133">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d8ca9-133">See also</span></span>

- [<span data-ttu-id="d8ca9-134">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="d8ca9-134">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="d8ca9-135">Интерфейс IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="d8ca9-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
