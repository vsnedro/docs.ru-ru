---
title: Метод ICorDebugManagedCallback2::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
ms.openlocfilehash: c5be9231bcd5aaddfa0cf1b0051f8e1184faef04
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687636"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="2b797-102">Метод ICorDebugManagedCallback2::Exception</span><span class="sxs-lookup"><span data-stu-id="2b797-102">ICorDebugManagedCallback2::Exception Method</span></span>

<span data-ttu-id="2b797-103">Уведомляет отладчик о запуске поиска обработчика исключений.</span><span class="sxs-lookup"><span data-stu-id="2b797-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b797-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b797-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b797-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b797-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="2b797-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий поток, в котором было создано исключение.</span><span class="sxs-lookup"><span data-stu-id="2b797-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="2b797-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором было создано исключение.</span><span class="sxs-lookup"><span data-stu-id="2b797-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="2b797-108">окне Указатель на объект ICorDebugFrame, представляющий кадр, как определено `dwEventType` параметром.</span><span class="sxs-lookup"><span data-stu-id="2b797-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="2b797-109">Дополнительные сведения см. в таблице в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="2b797-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="2b797-110">окне Целое число, задающее смещение, определяемое `dwEventType` параметром.</span><span class="sxs-lookup"><span data-stu-id="2b797-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="2b797-111">Дополнительные сведения см. в таблице в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="2b797-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="2b797-112">окне Значение перечисления CorDebugExceptionCallbackType, указывающее тип этого обратного вызова исключения.</span><span class="sxs-lookup"><span data-stu-id="2b797-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2b797-113">окне Значение перечисления [кордебужексцептионфлагс](cordebugexceptionflags-enumeration.md) , которое указывает дополнительные сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="2b797-113">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b797-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2b797-114">Remarks</span></span>  

 <span data-ttu-id="2b797-115">`Exception`Обратный вызов вызывается в различных точках на этапе поиска процесса обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="2b797-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="2b797-116">То есть он может быть вызван более одного раза при очистке исключения.</span><span class="sxs-lookup"><span data-stu-id="2b797-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="2b797-117">Обрабатываемое исключение может быть получено из объекта ICorDebugThread, на который ссылается `pThread` параметр.</span><span class="sxs-lookup"><span data-stu-id="2b797-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="2b797-118">Конкретный кадр и смещение определяются `dwEventType` параметром следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2b797-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="2b797-119">Значение параметра `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="2b797-119">Value of `dwEventType`</span></span>|<span data-ttu-id="2b797-120">Значение параметра `pFrame`</span><span class="sxs-lookup"><span data-stu-id="2b797-120">Value of `pFrame`</span></span>|<span data-ttu-id="2b797-121">Значение параметра `nOffset`</span><span class="sxs-lookup"><span data-stu-id="2b797-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="2b797-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="2b797-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="2b797-123">Кадр, вызвавший исключение.</span><span class="sxs-lookup"><span data-stu-id="2b797-123">The frame that threw the exception.</span></span>|<span data-ttu-id="2b797-124">Указатель инструкции в кадре.</span><span class="sxs-lookup"><span data-stu-id="2b797-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="2b797-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="2b797-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="2b797-126">Кадр пользовательского кода, ближайший к точке вызванного исключения.</span><span class="sxs-lookup"><span data-stu-id="2b797-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="2b797-127">Указатель инструкции в кадре.</span><span class="sxs-lookup"><span data-stu-id="2b797-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="2b797-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="2b797-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="2b797-129">Кадр, содержащий обработчик catch.</span><span class="sxs-lookup"><span data-stu-id="2b797-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="2b797-130">Смещение на языке MSIL, начинающееся с начала обработчика catch.</span><span class="sxs-lookup"><span data-stu-id="2b797-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="2b797-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="2b797-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="2b797-132">NULL</span><span class="sxs-lookup"><span data-stu-id="2b797-132">NULL</span></span>|<span data-ttu-id="2b797-133">Не определено.</span><span class="sxs-lookup"><span data-stu-id="2b797-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b797-134">Требования</span><span class="sxs-lookup"><span data-stu-id="2b797-134">Requirements</span></span>  

 <span data-ttu-id="2b797-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b797-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b797-136">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b797-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b797-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b797-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b797-138">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b797-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b797-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2b797-139">See also</span></span>

- [<span data-ttu-id="2b797-140">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="2b797-140">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="2b797-141">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="2b797-141">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
