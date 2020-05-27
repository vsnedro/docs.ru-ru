---
title: Метод IGCHost::GetThreadStats
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
ms.openlocfilehash: 4a7a2da58e197749d492f24c7a12134508efef57
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805235"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="fdbcc-102">Метод IGCHost::GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="fdbcc-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="fdbcc-103">Возвращает статистику по потокам для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="fdbcc-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdbcc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fdbcc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdbcc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fdbcc-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="fdbcc-106">окне Указатель на волокный файл cookie, указывающий поток, для которого необходимо получить статистику.</span><span class="sxs-lookup"><span data-stu-id="fdbcc-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="fdbcc-107">[вход, выход] Указатель на структуру [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) , содержащую статистику сборки мусора для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="fdbcc-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdbcc-108">Требования</span><span class="sxs-lookup"><span data-stu-id="fdbcc-108">Requirements</span></span>  
 <span data-ttu-id="fdbcc-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdbcc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdbcc-110">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="fdbcc-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="fdbcc-111">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fdbcc-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdbcc-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdbcc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdbcc-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="fdbcc-113">See also</span></span>

- [<span data-ttu-id="fdbcc-114">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="fdbcc-114">IGCHost Interface</span></span>](igchost-interface.md)
