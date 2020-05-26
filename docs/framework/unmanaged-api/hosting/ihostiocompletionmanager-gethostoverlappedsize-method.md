---
title: Метод IHostIoCompletionManager::GetHostOverlappedSize
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
ms.openlocfilehash: a97009a4ebc834d867dddcc350033c550364ea42
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804752"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="681e9-102">Метод IHostIoCompletionManager::GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="681e9-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="681e9-103">Возвращает размер любых пользовательских данных, которые узел намеревается добавить к запросам ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="681e9-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="681e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="681e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="681e9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="681e9-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="681e9-106">заполняет Указатель на число байтов, которое должна выделить среда CLR в дополнение к размеру `OVERLAPPED` объекта Win32.</span><span class="sxs-lookup"><span data-stu-id="681e9-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="681e9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="681e9-107">Return Value</span></span>  
  
|<span data-ttu-id="681e9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="681e9-108">HRESULT</span></span>|<span data-ttu-id="681e9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="681e9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="681e9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="681e9-110">S_OK</span></span>|<span data-ttu-id="681e9-111">`GetHostOverlappedSize`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="681e9-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="681e9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="681e9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="681e9-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="681e9-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="681e9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="681e9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="681e9-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="681e9-115">The call timed out.</span></span>|  
|<span data-ttu-id="681e9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="681e9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="681e9-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="681e9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="681e9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="681e9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="681e9-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="681e9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="681e9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="681e9-120">E_FAIL</span></span>|<span data-ttu-id="681e9-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="681e9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="681e9-122">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="681e9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="681e9-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="681e9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="681e9-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="681e9-124">Remarks</span></span>  
 <span data-ttu-id="681e9-125">Все асинхронные вызовы операций ввода-вывода в API платформы Windows принимают `OVERLAPPED` объект Win32, который предоставляет такую информацию, как расположение указателя файла.</span><span class="sxs-lookup"><span data-stu-id="681e9-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="681e9-126">Для поддержания состояния приложения, которые выполняют асинхронные вызовы операций ввода-вывода, обычно добавляют в структуру пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="681e9-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="681e9-127">`GetHostOverlappedSize`и [IHostIoCompletionManager:: инитиализехостоверлаппед](ihostiocompletionmanager-initializehostoverlapped-method.md) предоставляют возможность ведущему приложению включать такие пользовательские данные.</span><span class="sxs-lookup"><span data-stu-id="681e9-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="681e9-128">Среда CLR вызывает `GetHostOverlappedSize` метод, чтобы определить размер пользовательских данных, которые узел намеревается добавить к `OVERLAPPED` объекту.</span><span class="sxs-lookup"><span data-stu-id="681e9-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="681e9-129">`GetHostOverlappedSize`вызывается только один раз.</span><span class="sxs-lookup"><span data-stu-id="681e9-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="681e9-130">Пользовательские данные узла должны иметь одинаковый размер для каждого запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="681e9-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="681e9-131">Размер `OVERLAPPED` самого объекта не включается в значение `pcbSize` .</span><span class="sxs-lookup"><span data-stu-id="681e9-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="681e9-132">Дополнительные сведения о `OVERLAPPED` структуре см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="681e9-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="681e9-133">Требования</span><span class="sxs-lookup"><span data-stu-id="681e9-133">Requirements</span></span>  
 <span data-ttu-id="681e9-134">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="681e9-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="681e9-135">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="681e9-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="681e9-136">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="681e9-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="681e9-137">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="681e9-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="681e9-138">См. также статью</span><span class="sxs-lookup"><span data-stu-id="681e9-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="681e9-139">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="681e9-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="681e9-140">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="681e9-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
