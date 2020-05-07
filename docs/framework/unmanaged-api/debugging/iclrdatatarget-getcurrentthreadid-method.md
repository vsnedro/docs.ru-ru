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
ms.openlocfilehash: c75c55b64ff20728bc5695d0ddfe1b4f6deda4a6
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860652"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="9181d-102">Метод ICLRDataTarget::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="9181d-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="9181d-103">Возвращает идентификатор операционной системы для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="9181d-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9181d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9181d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9181d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9181d-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="9181d-106">заполняет Указатель на идентификатор операционной системы текущего потока для целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="9181d-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9181d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9181d-107">Remarks</span></span>  
 <span data-ttu-id="9181d-108">Если текущего потока для целевого процесса нет, `GetCurrentThreadID` метод может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9181d-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9181d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9181d-109">Requirements</span></span>  
 <span data-ttu-id="9181d-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9181d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9181d-111">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="9181d-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9181d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9181d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9181d-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9181d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9181d-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9181d-114">See also</span></span>

- [<span data-ttu-id="9181d-115">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="9181d-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
