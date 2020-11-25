---
title: Метод ICorConfiguration::SetGCThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 28b012bbe3f8c11ecd0afb8b5905336bd99c349c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724030"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="acdda-102">Метод ICorConfiguration::SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="acdda-102">ICorConfiguration::SetGCThreadControl Method</span></span>

<span data-ttu-id="acdda-103">Задает интерфейс обратного вызова для потоков планирования для задач, не относящихся к среде выполнения, которые в противном случае были бы заблокированы для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="acdda-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acdda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="acdda-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acdda-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="acdda-105">Parameters</span></span>  

 `pGCThreadControl`  
 <span data-ttu-id="acdda-106">окне Указатель на объект [IGCThreadControl](igcthreadcontrol-interface.md) , который уведомляет основное приложение о приостановке потоков для задач, не относящихся к среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="acdda-106">[in] A pointer to an [IGCThreadControl](igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acdda-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="acdda-107">Remarks</span></span>  

 <span data-ttu-id="acdda-108">Узел может выбрать один из обратных вызовов [IGCThreadControl:: среадисблоккингфорсуспенсион](igcthreadcontrol-threadisblockingforsuspension-method.md) , следует ли перепланировать поток.</span><span class="sxs-lookup"><span data-stu-id="acdda-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acdda-109">Требования</span><span class="sxs-lookup"><span data-stu-id="acdda-109">Requirements</span></span>  

 <span data-ttu-id="acdda-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acdda-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acdda-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="acdda-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acdda-112">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acdda-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acdda-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acdda-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acdda-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="acdda-114">See also</span></span>

- [<span data-ttu-id="acdda-115">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="acdda-115">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
