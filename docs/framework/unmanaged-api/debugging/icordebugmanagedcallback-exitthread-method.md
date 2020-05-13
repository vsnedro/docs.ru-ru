---
title: Метод ICorDebugManagedCallback::ExitThread
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
ms.openlocfilehash: 3ba1280aa44a9445f6af7fe9a8769b7cdc7edb66
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205247"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="d5c07-102">Метод ICorDebugManagedCallback::ExitThread</span><span class="sxs-lookup"><span data-stu-id="d5c07-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="d5c07-103">Уведомляет отладчик о том, что поток, который выполнял управляемый код, завершил работу.</span><span class="sxs-lookup"><span data-stu-id="d5c07-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5c07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5c07-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5c07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5c07-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d5c07-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="d5c07-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="d5c07-107">окне Указатель на объект ICorDebugThread, представляющий управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="d5c07-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5c07-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5c07-108">Remarks</span></span>  
 <span data-ttu-id="d5c07-109">После `ExitThread` запуска обратного вызова поток больше не будет отображаться в перечислениях потоков.</span><span class="sxs-lookup"><span data-stu-id="d5c07-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5c07-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d5c07-110">Requirements</span></span>  
 <span data-ttu-id="d5c07-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5c07-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5c07-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5c07-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5c07-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5c07-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5c07-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5c07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c07-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d5c07-115">See also</span></span>

- [<span data-ttu-id="d5c07-116">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d5c07-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
