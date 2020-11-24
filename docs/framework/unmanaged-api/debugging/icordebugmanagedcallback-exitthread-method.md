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
ms.openlocfilehash: 2ccb06b974cb17dff987ba42b647224cdc4c4ff2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688951"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="deb4c-102">Метод ICorDebugManagedCallback::ExitThread</span><span class="sxs-lookup"><span data-stu-id="deb4c-102">ICorDebugManagedCallback::ExitThread Method</span></span>

<span data-ttu-id="deb4c-103">Уведомляет отладчик о том, что поток, который выполнял управляемый код, завершил работу.</span><span class="sxs-lookup"><span data-stu-id="deb4c-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deb4c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="deb4c-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="deb4c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="deb4c-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="deb4c-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="deb4c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="deb4c-107">окне Указатель на объект ICorDebugThread, представляющий управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="deb4c-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="deb4c-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="deb4c-108">Remarks</span></span>  

 <span data-ttu-id="deb4c-109">После `ExitThread` запуска обратного вызова поток больше не будет отображаться в перечислениях потоков.</span><span class="sxs-lookup"><span data-stu-id="deb4c-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deb4c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="deb4c-110">Requirements</span></span>  

 <span data-ttu-id="deb4c-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="deb4c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb4c-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="deb4c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="deb4c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="deb4c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="deb4c-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deb4c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb4c-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="deb4c-115">See also</span></span>

- [<span data-ttu-id="deb4c-116">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="deb4c-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
