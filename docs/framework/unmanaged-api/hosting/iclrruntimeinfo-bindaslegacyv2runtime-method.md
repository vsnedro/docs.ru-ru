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
ms.openlocfilehash: 4390f379e5092cc59d123631f5e6d8da82e2bd7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703890"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="b2c0b-102">Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime</span><span class="sxs-lookup"><span data-stu-id="b2c0b-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="b2c0b-103">Привязывает текущую среду выполнения для всех устаревших решений политики активации среды CLR версии 2.</span><span class="sxs-lookup"><span data-stu-id="b2c0b-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2c0b-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b2c0b-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b2c0b-105">Return Value</span></span>  
 <span data-ttu-id="b2c0b-106">Этот метод возвращает следующие определенные значения HRESULT:</span><span class="sxs-lookup"><span data-stu-id="b2c0b-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="b2c0b-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2c0b-107">HRESULT</span></span>|<span data-ttu-id="b2c0b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b2c0b-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2c0b-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2c0b-109">S_OK</span></span>|<span data-ttu-id="b2c0b-110">Либо привязка выполнена успешно, либо эта среда выполнения уже была привязана к устаревшей среде выполнения политики активации CLR версии 2.</span><span class="sxs-lookup"><span data-stu-id="b2c0b-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="b2c0b-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="b2c0b-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="b2c0b-112">Другая среда выполнения уже привязана к устаревшей политике активации CLR версии 2.</span><span class="sxs-lookup"><span data-stu-id="b2c0b-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2c0b-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b2c0b-113">Remarks</span></span>  
 <span data-ttu-id="b2c0b-114">Если текущая среда выполнения уже привязана для всех устаревших решений политики активации CLR версии 2 (например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибута в [ \< элементе Startup>](../../configure-apps/file-schema/startup/startup-element.md) в файле конфигурации), этот метод не возвращает результат ошибки; вместо этого результат будет S_OK точно так же, как если бы метод успешно привязать устаревшую политику активации.</span><span class="sxs-lookup"><span data-stu-id="b2c0b-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2c0b-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b2c0b-115">Requirements</span></span>  
 <span data-ttu-id="b2c0b-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2c0b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2c0b-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="b2c0b-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b2c0b-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b2c0b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2c0b-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2c0b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2c0b-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b2c0b-120">See also</span></span>

- [<span data-ttu-id="b2c0b-121">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="b2c0b-121">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="b2c0b-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b2c0b-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b2c0b-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="b2c0b-123">Hosting</span></span>](index.md)
- [<span data-ttu-id="b2c0b-124">\<Элемент> запуска</span><span class="sxs-lookup"><span data-stu-id="b2c0b-124">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
