---
title: Функция LockClrVersion
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 09bcebfdcfea3d5728d404cdb6b5fb170a5432c3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008499"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="521e1-102">Функция LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="521e1-102">LockClrVersion Function</span></span>
<span data-ttu-id="521e1-103">Позволяет узлу определить, какая версия среды CLR будет использоваться в процессе перед явной инициализацией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="521e1-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="521e1-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="521e1-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="521e1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="521e1-105">Syntax</span></span>  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="521e1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="521e1-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="521e1-107">окне Функция, вызываемая средой CLR при инициализации.</span><span class="sxs-lookup"><span data-stu-id="521e1-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="521e1-108">окне Функция, вызываемая узлом для информирования среды CLR о начале инициализации.</span><span class="sxs-lookup"><span data-stu-id="521e1-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="521e1-109">окне Функция, вызываемая узлом для информирования среды CLR о завершении инициализации.</span><span class="sxs-lookup"><span data-stu-id="521e1-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="521e1-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="521e1-110">Return Value</span></span>  
 <span data-ttu-id="521e1-111">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="521e1-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="521e1-112">Код возврата</span><span class="sxs-lookup"><span data-stu-id="521e1-112">Return code</span></span>|<span data-ttu-id="521e1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="521e1-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="521e1-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="521e1-114">S_OK</span></span>|<span data-ttu-id="521e1-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="521e1-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="521e1-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="521e1-116">E_INVALIDARG</span></span>|<span data-ttu-id="521e1-117">Один или несколько аргументов имеют значение null.</span><span class="sxs-lookup"><span data-stu-id="521e1-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="521e1-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="521e1-118">Remarks</span></span>  
 <span data-ttu-id="521e1-119">Узел вызывает `LockClrVersion` перед инициализацией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="521e1-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="521e1-120">`LockClrVersion`принимает три параметра, все из которых являются обратными вызовами типа [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="521e1-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="521e1-121">Этот тип определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="521e1-121">This type is defined as follows.</span></span>  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="521e1-122">При инициализации среды выполнения выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="521e1-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="521e1-123">Узел вызывает [CorBindToRuntimeEx](corbindtoruntimeex-function.md) или одну из других функций инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="521e1-123">The host calls [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="521e1-124">Кроме того, узел может инициализировать среду выполнения с помощью активации объекта COM.</span><span class="sxs-lookup"><span data-stu-id="521e1-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="521e1-125">Среда выполнения вызывает функцию, указанную `hostCallback` параметром.</span><span class="sxs-lookup"><span data-stu-id="521e1-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="521e1-126">Функция, указанная с помощью, `hostCallback` выполняет следующую последовательность вызовов:</span><span class="sxs-lookup"><span data-stu-id="521e1-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="521e1-127">Функция, заданная `pBeginHostSetup` параметром.</span><span class="sxs-lookup"><span data-stu-id="521e1-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="521e1-128">`CorBindToRuntimeEx`(или другую функцию инициализации среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="521e1-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="521e1-129">[ICLRRuntimeHost:: SetHostControl](iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="521e1-129">[ICLRRuntimeHost::SetHostControl](iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="521e1-130">[ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="521e1-130">[ICLRRuntimeHost::Start](iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="521e1-131">Функция, заданная `pEndHostSetup` параметром.</span><span class="sxs-lookup"><span data-stu-id="521e1-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="521e1-132">Все вызовы из `pBeginHostSetup` в `pEndHostSetup` должны выполняться в одном потоке или Fiber с одним и тем же логическим стеком.</span><span class="sxs-lookup"><span data-stu-id="521e1-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="521e1-133">Этот поток может отличаться от потока, в котором `hostCallback` вызывается.</span><span class="sxs-lookup"><span data-stu-id="521e1-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="521e1-134">Требования</span><span class="sxs-lookup"><span data-stu-id="521e1-134">Requirements</span></span>  
 <span data-ttu-id="521e1-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="521e1-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="521e1-136">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="521e1-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="521e1-137">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="521e1-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="521e1-138">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="521e1-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="521e1-139">См. также статью</span><span class="sxs-lookup"><span data-stu-id="521e1-139">See also</span></span>

- [<span data-ttu-id="521e1-140">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="521e1-140">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
