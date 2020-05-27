---
title: Метод IGCHost::SetVirtualMemLimit
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: 93ed63b4abacce1d8943434965aacf67190631b6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805191"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="51437-102">Метод IGCHost::SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="51437-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="51437-103">Задает максимальный размер виртуальной памяти среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="51437-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51437-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51437-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51437-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="51437-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="51437-106">окне Максимальный размер виртуальной памяти среды выполнения в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="51437-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51437-107">Замечания</span><span class="sxs-lookup"><span data-stu-id="51437-107">Remarks</span></span>  
 <span data-ttu-id="51437-108">Максимальный размер виртуальной памяти среды выполнения можно изменить динамически.</span><span class="sxs-lookup"><span data-stu-id="51437-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51437-109">Требования</span><span class="sxs-lookup"><span data-stu-id="51437-109">Requirements</span></span>  
 <span data-ttu-id="51437-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51437-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51437-111">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="51437-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="51437-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="51437-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51437-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51437-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51437-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="51437-114">See also</span></span>

- [<span data-ttu-id="51437-115">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="51437-115">IGCHost Interface</span></span>](igchost-interface.md)
