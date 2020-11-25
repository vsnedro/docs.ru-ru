---
title: Метод ICorDebugManagedCallback3::CustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: f30c9b6746d0e1594994870a96e94eb8105e4c94
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700838"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="4b13b-102">Метод ICorDebugManagedCallback3::CustomNotification</span><span class="sxs-lookup"><span data-stu-id="4b13b-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>

<span data-ttu-id="4b13b-103">Указывает, что было создано пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="4b13b-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b13b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b13b-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b13b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b13b-105">Parameters</span></span>  

 `pThread`  
 <span data-ttu-id="4b13b-106">окне Указатель на поток, создавший уведомление.</span><span class="sxs-lookup"><span data-stu-id="4b13b-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="4b13b-107">окне Указатель на домен приложения, содержащий поток, вызвавший уведомление.</span><span class="sxs-lookup"><span data-stu-id="4b13b-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b13b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4b13b-108">Return Value</span></span>  

 <span data-ttu-id="4b13b-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="4b13b-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4b13b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b13b-110">HRESULT</span></span>|<span data-ttu-id="4b13b-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="4b13b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b13b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b13b-112">S_OK</span></span>|<span data-ttu-id="4b13b-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="4b13b-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4b13b-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="4b13b-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b13b-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b13b-115">Remarks</span></span>  

 <span data-ttu-id="4b13b-116">Последующий вызов метода [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) извлекает объект потока, переданный в <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="4b13b-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4b13b-117">Тип объекта потока должен быть ранее включен путем вызова метода [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4b13b-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="4b13b-118">Отладчик может считывать параметры конкретного типа из полей объекта потока и может сохранять ответы в полях.</span><span class="sxs-lookup"><span data-stu-id="4b13b-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="4b13b-119">Интерфейс [ICorDebug](icordebug-interface.md) не накладывает политики на типы уведомлений или их содержимое, а семантика уведомлений является строго контрактом между отладчиками, приложениями и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4b13b-119">The [ICorDebug](icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b13b-120">Требования</span><span class="sxs-lookup"><span data-stu-id="4b13b-120">Requirements</span></span>  

 <span data-ttu-id="4b13b-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b13b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b13b-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b13b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b13b-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b13b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b13b-124">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b13b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b13b-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4b13b-125">See also</span></span>

- [<span data-ttu-id="4b13b-126">Интерфейс ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="4b13b-126">ICorDebugManagedCallback3 Interface</span></span>](icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="4b13b-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4b13b-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4b13b-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="4b13b-128">Debugging</span></span>](index.md)
