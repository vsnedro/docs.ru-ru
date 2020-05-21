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
ms.openlocfilehash: 85a7adddf395e07297c8fb6ceab4aa81e0aaf012
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762205"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="8fc65-102">Метод ICLRRuntimeInfo::IsStarted</span><span class="sxs-lookup"><span data-stu-id="8fc65-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="8fc65-103">Указывает, была ли запущена среда выполнения (т. е. был ли вызван [метод ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) и он был успешно выполнен).</span><span class="sxs-lookup"><span data-stu-id="8fc65-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fc65-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fc65-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8fc65-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="8fc65-106">[out] `true` значение, если среда выполнения запущена; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="8fc65-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="8fc65-107">заполняет Возвращает флаги, которые использовались для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8fc65-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fc65-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8fc65-108">Return Value</span></span>  
 <span data-ttu-id="8fc65-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="8fc65-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8fc65-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8fc65-110">HRESULT</span></span>|<span data-ttu-id="8fc65-111">Описание</span><span class="sxs-lookup"><span data-stu-id="8fc65-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8fc65-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8fc65-112">S_OK</span></span>|<span data-ttu-id="8fc65-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="8fc65-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="8fc65-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8fc65-114">E_NOTIMPL</span></span>|<span data-ttu-id="8fc65-115">Версия среды CLR предшествует версии CLR в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8fc65-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fc65-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8fc65-116">Remarks</span></span>  
 <span data-ttu-id="8fc65-117">Этот метод не работает с версиями CLR, предшествующими версии CLR в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8fc65-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fc65-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8fc65-118">Requirements</span></span>  
 <span data-ttu-id="8fc65-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fc65-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fc65-120">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="8fc65-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8fc65-121">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8fc65-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8fc65-122">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fc65-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc65-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8fc65-123">See also</span></span>

- [<span data-ttu-id="8fc65-124">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="8fc65-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="8fc65-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="8fc65-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="8fc65-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="8fc65-126">Hosting</span></span>](index.md)
