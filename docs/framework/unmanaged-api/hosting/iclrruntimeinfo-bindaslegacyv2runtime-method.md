---
title: Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
ms.openlocfilehash: f0a03ecce49bbc3c1c03d037c9be31a8e994259d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732101"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="72bd1-102">Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime</span><span class="sxs-lookup"><span data-stu-id="72bd1-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>

<span data-ttu-id="72bd1-103">Привязывает текущую среду выполнения для всех устаревших решений политики активации среды CLR версии 2.</span><span class="sxs-lookup"><span data-stu-id="72bd1-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72bd1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72bd1-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="72bd1-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="72bd1-105">Return Value</span></span>  

 <span data-ttu-id="72bd1-106">Этот метод возвращает следующие определенные значения HRESULT:</span><span class="sxs-lookup"><span data-stu-id="72bd1-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="72bd1-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72bd1-107">HRESULT</span></span>|<span data-ttu-id="72bd1-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="72bd1-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72bd1-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="72bd1-109">S_OK</span></span>|<span data-ttu-id="72bd1-110">Либо привязка выполнена успешно, либо эта среда выполнения уже была привязана к устаревшей среде выполнения политики активации CLR версии 2.</span><span class="sxs-lookup"><span data-stu-id="72bd1-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="72bd1-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="72bd1-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="72bd1-112">Другая среда выполнения уже привязана к устаревшей политике активации CLR версии 2.</span><span class="sxs-lookup"><span data-stu-id="72bd1-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72bd1-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="72bd1-113">Remarks</span></span>  

 <span data-ttu-id="72bd1-114">Если текущая среда выполнения уже привязана для всех устаревших решений политики активации CLR версии 2 (например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибута [ \<startup> элемента](../../configure-apps/file-schema/startup/startup-element.md) в файле конфигурации), этот метод не возвращает результат ошибки; вместо этого результат S_OK, как если бы метод успешно привязать политику активации прежних версий.</span><span class="sxs-lookup"><span data-stu-id="72bd1-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72bd1-115">Требования</span><span class="sxs-lookup"><span data-stu-id="72bd1-115">Requirements</span></span>  

 <span data-ttu-id="72bd1-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72bd1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72bd1-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="72bd1-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="72bd1-118">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72bd1-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72bd1-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72bd1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72bd1-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="72bd1-120">See also</span></span>

- [<span data-ttu-id="72bd1-121">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="72bd1-121">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="72bd1-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="72bd1-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="72bd1-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="72bd1-123">Hosting</span></span>](index.md)
- [<span data-ttu-id="72bd1-124">\<startup> Элемент</span><span class="sxs-lookup"><span data-stu-id="72bd1-124">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
