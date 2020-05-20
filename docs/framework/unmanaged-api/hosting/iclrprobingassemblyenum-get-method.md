---
title: Метод ICLRProbingAssemblyEnum::Get
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
ms.openlocfilehash: ea66c142afc097d1003df4e7f5f5b960a91e2ab0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703383"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="4fcd0-102">Метод ICLRProbingAssemblyEnum::Get</span><span class="sxs-lookup"><span data-stu-id="4fcd0-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="4fcd0-103">Возвращает удостоверение сборки по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fcd0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fcd0-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fcd0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4fcd0-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="4fcd0-106">окне Отсчитываемый от нуля индекс возвращаемого удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="4fcd0-107">заполняет Буфер, содержащий данные удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="4fcd0-108">[вход, выход] Размер `pwzBuffer` буфера.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fcd0-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4fcd0-109">Return Value</span></span>  
  
|<span data-ttu-id="4fcd0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4fcd0-110">HRESULT</span></span>|<span data-ttu-id="4fcd0-111">Описание</span><span class="sxs-lookup"><span data-stu-id="4fcd0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4fcd0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4fcd0-112">S_OK</span></span>|<span data-ttu-id="4fcd0-113">`Get`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="4fcd0-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4fcd0-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4fcd0-115">`pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="4fcd0-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="4fcd0-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="4fcd0-117">Перечисление не содержит больше элементов.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="4fcd0-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4fcd0-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4fcd0-119">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4fcd0-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4fcd0-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4fcd0-121">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-121">The call timed out.</span></span>|  
|<span data-ttu-id="4fcd0-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4fcd0-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4fcd0-123">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4fcd0-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4fcd0-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4fcd0-125">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4fcd0-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4fcd0-126">E_FAIL</span></span>|<span data-ttu-id="4fcd0-127">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4fcd0-128">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4fcd0-129">Последующие вызовы любых методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fcd0-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4fcd0-130">Remarks</span></span>  
 <span data-ttu-id="4fcd0-131">Удостоверение с индексом 0 — это удостоверение, относящееся к архитектуре процессора.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="4fcd0-132">Удостоверение с индексом 1 — это нейтральная к архитектуре сборка для промежуточного языка Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="4fcd0-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="4fcd0-133">Удостоверение с индексом 2 не содержит сведений об архитектуре.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="4fcd0-134">`Get`обычно вызывается дважды.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-134">`Get` is typically called twice.</span></span> <span data-ttu-id="4fcd0-135">Первый вызов предоставляет значение NULL для `pwzBuffer` , а устанавливает `pcchBufferSize` в качестве размера, соответствующего `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="4fcd0-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="4fcd0-136">Второй вызов предоставляет соответствующий размер `pwzBuffer` и содержит канонические данные удостоверений сборки после завершения.</span><span class="sxs-lookup"><span data-stu-id="4fcd0-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fcd0-137">Требования</span><span class="sxs-lookup"><span data-stu-id="4fcd0-137">Requirements</span></span>  
 <span data-ttu-id="4fcd0-138">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fcd0-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fcd0-139">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4fcd0-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fcd0-140">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4fcd0-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fcd0-141">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fcd0-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fcd0-142">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="4fcd0-142">See also</span></span>

- [<span data-ttu-id="4fcd0-143">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="4fcd0-143">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="4fcd0-144">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="4fcd0-144">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
