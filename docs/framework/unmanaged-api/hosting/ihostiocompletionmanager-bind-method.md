---
title: Метод IHostIoCompletionManager::Bind
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
ms.openlocfilehash: 5231db8de6129ed593e4e0d508b312b7034c01f0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733910"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="12cfa-102">Метод IHostIoCompletionManager::Bind</span><span class="sxs-lookup"><span data-stu-id="12cfa-102">IHostIoCompletionManager::Bind Method</span></span>

<span data-ttu-id="12cfa-103">Привязывает указанный маркер к порту завершения ввода-вывода, созданному предыдущим вызовом метода [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="12cfa-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12cfa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12cfa-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12cfa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12cfa-105">Parameters</span></span>  

 `hPort`  
 <span data-ttu-id="12cfa-106">окне Порт завершения ввода-вывода, к которому выполняется привязка `hHandle` .</span><span class="sxs-lookup"><span data-stu-id="12cfa-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="12cfa-107">Если значение `hPort` равно null, `hHandle` привязывается к порту завершения ввода-вывода по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="12cfa-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="12cfa-108">окне Обработчик операционной системы для привязки `hPort` .</span><span class="sxs-lookup"><span data-stu-id="12cfa-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12cfa-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="12cfa-109">Return Value</span></span>  
  
|<span data-ttu-id="12cfa-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12cfa-110">HRESULT</span></span>|<span data-ttu-id="12cfa-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="12cfa-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12cfa-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="12cfa-112">S_OK</span></span>|<span data-ttu-id="12cfa-113">`Bind` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="12cfa-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="12cfa-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="12cfa-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="12cfa-115">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="12cfa-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="12cfa-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="12cfa-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="12cfa-117">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="12cfa-117">The call timed out.</span></span>|  
|<span data-ttu-id="12cfa-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="12cfa-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="12cfa-119">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="12cfa-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="12cfa-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="12cfa-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="12cfa-121">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="12cfa-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="12cfa-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="12cfa-122">E_FAIL</span></span>|<span data-ttu-id="12cfa-123">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="12cfa-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="12cfa-124">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="12cfa-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="12cfa-125">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="12cfa-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12cfa-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="12cfa-126">Remarks</span></span>  

 <span data-ttu-id="12cfa-127">Порт завершения ввода-вывода создается с помощью вызова `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="12cfa-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="12cfa-128">Среда CLR вызывает `Bind` для привязки маркера к этому порту.</span><span class="sxs-lookup"><span data-stu-id="12cfa-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12cfa-129">По завершении запроса ввода-вывода узел должен вызвать метод [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="12cfa-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12cfa-130">Требования</span><span class="sxs-lookup"><span data-stu-id="12cfa-130">Requirements</span></span>  

 <span data-ttu-id="12cfa-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12cfa-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12cfa-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="12cfa-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12cfa-133">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12cfa-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12cfa-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12cfa-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cfa-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="12cfa-135">See also</span></span>

- [<span data-ttu-id="12cfa-136">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="12cfa-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
