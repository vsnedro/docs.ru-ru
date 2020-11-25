---
title: Метод ICLRRuntimeInfo::IsStarted
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 1dfeb6101a6b8e33ab2fe35f318087d7f1834b6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714891"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="3e96c-102">Метод ICLRRuntimeInfo::IsStarted</span><span class="sxs-lookup"><span data-stu-id="3e96c-102">ICLRRuntimeInfo::IsStarted Method</span></span>

<span data-ttu-id="3e96c-103">Указывает, была ли запущена среда выполнения (т. е. был ли вызван [метод ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) и он был успешно выполнен).</span><span class="sxs-lookup"><span data-stu-id="3e96c-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e96c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e96c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e96c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e96c-105">Parameters</span></span>  

 `pbStarted`  
 <span data-ttu-id="3e96c-106">[out] `true` значение, если среда выполнения запущена; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="3e96c-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="3e96c-107">заполняет Возвращает флаги, которые использовались для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3e96c-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e96c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3e96c-108">Return Value</span></span>  

 <span data-ttu-id="3e96c-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="3e96c-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3e96c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e96c-110">HRESULT</span></span>|<span data-ttu-id="3e96c-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="3e96c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e96c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e96c-112">S_OK</span></span>|<span data-ttu-id="3e96c-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="3e96c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="3e96c-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3e96c-114">E_NOTIMPL</span></span>|<span data-ttu-id="3e96c-115">Версия среды CLR предшествует версии CLR в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3e96c-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e96c-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3e96c-116">Remarks</span></span>  

 <span data-ttu-id="3e96c-117">Этот метод не работает с версиями CLR, предшествующими версии CLR в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3e96c-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e96c-118">Требования</span><span class="sxs-lookup"><span data-stu-id="3e96c-118">Requirements</span></span>  

 <span data-ttu-id="3e96c-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e96c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e96c-120">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="3e96c-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3e96c-121">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e96c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e96c-122">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e96c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e96c-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3e96c-123">See also</span></span>

- [<span data-ttu-id="3e96c-124">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="3e96c-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="3e96c-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3e96c-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="3e96c-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="3e96c-126">Hosting</span></span>](index.md)
