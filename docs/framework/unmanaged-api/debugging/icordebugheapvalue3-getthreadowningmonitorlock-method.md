---
title: Метод ICorDebugHeapValue3::GetThreadOwningMonitorLock
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
ms.openlocfilehash: fef0902aedbcd8572d2dc67fae7927f754af4489
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723315"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="067a6-102">Метод ICorDebugHeapValue3::GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="067a6-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>

<span data-ttu-id="067a6-103">Возвращает управляемый поток, которому принадлежит блокировка монитора для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="067a6-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="067a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="067a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="067a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="067a6-105">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="067a6-106">заполняет Управляемый поток, которому принадлежит блокировка монитора для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="067a6-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="067a6-107">заполняет Количество случаев, в течение которых этот поток должен снять блокировку, прежде чем возвратить его в качестве владельца.</span><span class="sxs-lookup"><span data-stu-id="067a6-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="067a6-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="067a6-108">Return Value</span></span>  

 <span data-ttu-id="067a6-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="067a6-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="067a6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="067a6-110">HRESULT</span></span>|<span data-ttu-id="067a6-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="067a6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="067a6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="067a6-112">S_OK</span></span>|<span data-ttu-id="067a6-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="067a6-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="067a6-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="067a6-114">S_FALSE</span></span>|<span data-ttu-id="067a6-115">Ни один управляемый поток не владеет блокировкой монитора для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="067a6-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="067a6-116">Исключения</span><span class="sxs-lookup"><span data-stu-id="067a6-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="067a6-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="067a6-117">Remarks</span></span>  

 <span data-ttu-id="067a6-118">Если управляемый поток владеет блокировкой монитора для этого объекта:</span><span class="sxs-lookup"><span data-stu-id="067a6-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="067a6-119">Метод возвращает S_OK.</span><span class="sxs-lookup"><span data-stu-id="067a6-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="067a6-120">Объект потока действителен до тех пор, пока поток не завершит работу.</span><span class="sxs-lookup"><span data-stu-id="067a6-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="067a6-121">Если ни один управляемый поток не владеет блокировкой монитора для этого объекта `ppThread` и `pAcquisitionCount` не изменяется, а метод возвращает S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="067a6-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="067a6-122">Если `ppThread` или не `pAcquisitionCount` является допустимым указателем, результат не определен.</span><span class="sxs-lookup"><span data-stu-id="067a6-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="067a6-123">Если возникает ошибка, которая не может определить, какой поток владеет блокировкой монитора для этого объекта, метод возвращает значение HRESULT, которое указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="067a6-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="067a6-124">Требования</span><span class="sxs-lookup"><span data-stu-id="067a6-124">Requirements</span></span>  

 <span data-ttu-id="067a6-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="067a6-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="067a6-126">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="067a6-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="067a6-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="067a6-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="067a6-128">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="067a6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="067a6-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="067a6-129">See also</span></span>

- [<span data-ttu-id="067a6-130">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="067a6-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="067a6-131">Отладка</span><span class="sxs-lookup"><span data-stu-id="067a6-131">Debugging</span></span>](index.md)
