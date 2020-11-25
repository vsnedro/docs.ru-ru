---
title: Метод ICorDebugProcess::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
ms.openlocfilehash: 3be689e5c1474bcbfbca72a14a298762dc2e7a90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724550"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="22ee7-102">Метод ICorDebugProcess::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="22ee7-102">ICorDebugProcess::GetThreadContext Method</span></span>

<span data-ttu-id="22ee7-103">Возвращает контекст для данного потока в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="22ee7-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ee7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22ee7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22ee7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="22ee7-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="22ee7-106">окне Идентификатор потока, для которого извлекается контекст.</span><span class="sxs-lookup"><span data-stu-id="22ee7-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="22ee7-107">[in] Размер массива `context`.</span><span class="sxs-lookup"><span data-stu-id="22ee7-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="22ee7-108">[вход, выход] Массив байтов, описывающих контекст потока.</span><span class="sxs-lookup"><span data-stu-id="22ee7-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="22ee7-109">Контекст указывает архитектуру процессора, на котором работает поток.</span><span class="sxs-lookup"><span data-stu-id="22ee7-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22ee7-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="22ee7-110">Remarks</span></span>  

 <span data-ttu-id="22ee7-111">Отладчик должен вызывать этот метод вместо `GetThreadContext` метода Win32, так как поток может находиться в состоянии "перехвачено", в котором его контекст временно изменен.</span><span class="sxs-lookup"><span data-stu-id="22ee7-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="22ee7-112">Этот метод следует использовать только в том случае, если поток находится в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="22ee7-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="22ee7-113">Используйте [ICorDebugRegisterSet](icordebugregisterset-interface.md) для потоков в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="22ee7-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="22ee7-114">Возвращаемые данные — это структура контекста для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="22ee7-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="22ee7-115">Как и в случае с `GetThreadContext` методом Win32, вызывающий объект должен инициализировать `context` параметр перед вызовом этого метода.</span><span class="sxs-lookup"><span data-stu-id="22ee7-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22ee7-116">Требования</span><span class="sxs-lookup"><span data-stu-id="22ee7-116">Requirements</span></span>  

 <span data-ttu-id="22ee7-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22ee7-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ee7-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22ee7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22ee7-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22ee7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22ee7-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22ee7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
