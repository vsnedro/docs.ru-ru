---
title: Метод IGCHost::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
ms.openlocfilehash: 3b0c11ac9d827bd252018172e2337df653054a7b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805199"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="c1665-102">Метод IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="c1665-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="c1665-103">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="c1665-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c1665-104">Начиная с .NET Framework 4,5 можно задать размер сегмента и максимальный размер поколения 0 в значениях, превышающих `DWORD` использование метода [IGCHost2:: SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c1665-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1665-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1665-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1665-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1665-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="c1665-107">окне Размер сегмента, используемого системой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c1665-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="c1665-108">окне Максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="c1665-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1665-109">Замечания</span><span class="sxs-lookup"><span data-stu-id="c1665-109">Remarks</span></span>  
 <span data-ttu-id="c1665-110">`SetGCStartupLimits`Метод может быть вызван только один раз.</span><span class="sxs-lookup"><span data-stu-id="c1665-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="c1665-111">Эти значения нельзя изменить позже.</span><span class="sxs-lookup"><span data-stu-id="c1665-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1665-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c1665-112">Requirements</span></span>  
 <span data-ttu-id="c1665-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1665-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1665-114">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="c1665-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="c1665-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c1665-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1665-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1665-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1665-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c1665-117">See also</span></span>

- [<span data-ttu-id="c1665-118">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="c1665-118">IGCHost Interface</span></span>](igchost-interface.md)
