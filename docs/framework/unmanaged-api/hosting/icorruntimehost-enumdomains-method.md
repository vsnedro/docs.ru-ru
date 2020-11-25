---
title: Метод ICorRuntimeHost::EnumDomains
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
ms.openlocfilehash: f4338429dc24bf5196b92d3f18e73c98442f61e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720666"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="716d6-102">Метод ICorRuntimeHost::EnumDomains</span><span class="sxs-lookup"><span data-stu-id="716d6-102">ICorRuntimeHost::EnumDomains Method</span></span>

<span data-ttu-id="716d6-103">Возвращает перечислитель для доменов в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="716d6-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="716d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="716d6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="716d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="716d6-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="716d6-106">заполняет Перечислитель для доменов.</span><span class="sxs-lookup"><span data-stu-id="716d6-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="716d6-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="716d6-107">Return Value</span></span>  
  
|<span data-ttu-id="716d6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="716d6-108">HRESULT</span></span>|<span data-ttu-id="716d6-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="716d6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="716d6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="716d6-110">S_OK</span></span>|<span data-ttu-id="716d6-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="716d6-111">The operation was successful.</span></span>|  
|<span data-ttu-id="716d6-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="716d6-112">S_FALSE</span></span>|<span data-ttu-id="716d6-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="716d6-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="716d6-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="716d6-114">E_FAIL</span></span>|<span data-ttu-id="716d6-115">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="716d6-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="716d6-116">Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="716d6-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="716d6-117">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="716d6-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="716d6-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="716d6-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="716d6-119">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="716d6-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="716d6-120">Требования</span><span class="sxs-lookup"><span data-stu-id="716d6-120">Requirements</span></span>  

 <span data-ttu-id="716d6-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="716d6-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="716d6-122">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="716d6-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="716d6-123">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="716d6-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="716d6-124">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="716d6-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716d6-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="716d6-125">See also</span></span>

- [<span data-ttu-id="716d6-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="716d6-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
