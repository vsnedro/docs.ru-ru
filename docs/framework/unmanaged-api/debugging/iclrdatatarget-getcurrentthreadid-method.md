---
title: Метод ICLRDataTarget::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
ms.openlocfilehash: 3a355822710394e9351f10be78dea283e2e9907c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703595"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="40698-102">Метод ICLRDataTarget::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="40698-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>

<span data-ttu-id="40698-103">Возвращает идентификатор операционной системы для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="40698-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40698-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40698-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40698-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="40698-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="40698-106">заполняет Указатель на идентификатор операционной системы текущего потока для целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="40698-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40698-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="40698-107">Remarks</span></span>  

 <span data-ttu-id="40698-108">Если текущего потока для целевого процесса нет, `GetCurrentThreadID` метод может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="40698-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40698-109">Требования</span><span class="sxs-lookup"><span data-stu-id="40698-109">Requirements</span></span>  

 <span data-ttu-id="40698-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40698-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40698-111">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="40698-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="40698-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40698-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40698-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40698-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40698-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="40698-114">See also</span></span>

- [<span data-ttu-id="40698-115">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="40698-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
