---
title: Метод ICorRuntimeHost::NextDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
ms.openlocfilehash: 598c46d50d7b4a67c1b2c0d844c9b12deb12a428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671373"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="ce55e-102">Метод ICorRuntimeHost::NextDomain</span><span class="sxs-lookup"><span data-stu-id="ce55e-102">ICorRuntimeHost::NextDomain Method</span></span>

<span data-ttu-id="ce55e-103">Возвращает указатель интерфейса на следующий домен в перечислении.</span><span class="sxs-lookup"><span data-stu-id="ce55e-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce55e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce55e-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce55e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce55e-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="ce55e-106">окне Перечислитель, полученный при вызове [енумдомаинс](icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="ce55e-106">[in] The enumerator that was obtained through a call to [EnumDomains](icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="ce55e-107">заполняет Указатель интерфейса на <xref:System._AppDomain?displayProperty=nameWithType> тип, представляющий следующий домен в перечислении, или значение null, если другие домены не существуют.</span><span class="sxs-lookup"><span data-stu-id="ce55e-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce55e-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ce55e-108">Return Value</span></span>  
  
|<span data-ttu-id="ce55e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce55e-109">HRESULT</span></span>|<span data-ttu-id="ce55e-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="ce55e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce55e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce55e-111">S_OK</span></span>|<span data-ttu-id="ce55e-112">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="ce55e-112">The operation was successful.</span></span>|  
|<span data-ttu-id="ce55e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ce55e-113">S_FALSE</span></span>|<span data-ttu-id="ce55e-114">Не удалось завершить операцию, или в перечислении больше нет доменов.</span><span class="sxs-lookup"><span data-stu-id="ce55e-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="ce55e-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce55e-115">E_FAIL</span></span>|<span data-ttu-id="ce55e-116">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ce55e-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ce55e-117">Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ce55e-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="ce55e-118">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ce55e-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ce55e-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce55e-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce55e-120">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ce55e-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce55e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="ce55e-121">Requirements</span></span>  

 <span data-ttu-id="ce55e-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce55e-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce55e-123">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ce55e-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce55e-124">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce55e-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce55e-125">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="ce55e-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce55e-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ce55e-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="ce55e-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ce55e-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
