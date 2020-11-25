---
title: Метод IGCHost2::SetGCStartupLimitsEx
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
ms.openlocfilehash: 4dca62903a123765ceb8bb251b79455ad0e4730a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726812"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="264e4-102">Метод IGCHost2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="264e4-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>

<span data-ttu-id="264e4-103">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="264e4-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="264e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="264e4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="264e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="264e4-105">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="264e4-106">окне Размер сегмента, используемого системой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="264e4-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="264e4-107">окне Максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="264e4-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="264e4-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="264e4-108">Remarks</span></span>  

 <span data-ttu-id="264e4-109">Значения, которые `SetGCStartupLimitsEx` задаются, можно указать только перед запуском узла.</span><span class="sxs-lookup"><span data-stu-id="264e4-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="264e4-110">Эти значения нельзя изменить позже.</span><span class="sxs-lookup"><span data-stu-id="264e4-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="264e4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="264e4-111">Requirements</span></span>  

 <span data-ttu-id="264e4-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="264e4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="264e4-113">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="264e4-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="264e4-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="264e4-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="264e4-115">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="264e4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="264e4-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="264e4-116">See also</span></span>

- [<span data-ttu-id="264e4-117">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="264e4-117">IGCHost2 Interface</span></span>](igchost2-interface.md)
