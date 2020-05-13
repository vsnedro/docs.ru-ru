---
title: Метод ICorDebugManagedCallback::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
ms.openlocfilehash: 2d0461709accf1a9300c072b62bd58734cb33fb8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209816"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="9315d-102">Метод ICorDebugManagedCallback::Exception</span><span class="sxs-lookup"><span data-stu-id="9315d-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="9315d-103">Уведомляет отладчик о появлении исключения из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9315d-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9315d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9315d-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9315d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9315d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9315d-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в котором было создано исключение.</span><span class="sxs-lookup"><span data-stu-id="9315d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="9315d-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором было создано исключение.</span><span class="sxs-lookup"><span data-stu-id="9315d-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="9315d-108">окне Если это значение равно `false` , исключение еще не было обработано приложением; в противном случае исключение не обрабатывается, и процесс завершится.</span><span class="sxs-lookup"><span data-stu-id="9315d-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9315d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="9315d-109">Remarks</span></span>  
 <span data-ttu-id="9315d-110">Конкретное исключение можно получить из объекта потока.</span><span class="sxs-lookup"><span data-stu-id="9315d-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9315d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9315d-111">Requirements</span></span>  
 <span data-ttu-id="9315d-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9315d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9315d-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9315d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9315d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9315d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9315d-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9315d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9315d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9315d-116">See also</span></span>

- [<span data-ttu-id="9315d-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9315d-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
