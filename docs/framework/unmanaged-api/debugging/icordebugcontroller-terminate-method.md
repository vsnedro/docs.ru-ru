---
title: Метод ICorDebugController::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
ms.openlocfilehash: eade3fd5d946c44ae4a77c571f762709de3cef40
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976568"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="ed9a8-102">Метод ICorDebugController::Terminate</span><span class="sxs-lookup"><span data-stu-id="ed9a8-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="ed9a8-103">Завершает процесс с указанным кодом выхода.</span><span class="sxs-lookup"><span data-stu-id="ed9a8-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed9a8-104">Этот метод является оболочкой для функции Win32 `TerminateProcess` .</span><span class="sxs-lookup"><span data-stu-id="ed9a8-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="ed9a8-105">Таким образом `Terminate` , использует код выхода точно так же, как функция Win32 `TerminateProcess` использует ее.</span><span class="sxs-lookup"><span data-stu-id="ed9a8-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed9a8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed9a8-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed9a8-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed9a8-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="ed9a8-108">окне Числовое значение, которое является кодом выхода.</span><span class="sxs-lookup"><span data-stu-id="ed9a8-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="ed9a8-109">Допустимые числовые значения определяются в Винбасе. h.</span><span class="sxs-lookup"><span data-stu-id="ed9a8-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed9a8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ed9a8-110">Remarks</span></span>  
 <span data-ttu-id="ed9a8-111">Если `Terminate` процесс останавливается при вызове, процесс должен быть продолжен с помощью метода [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , чтобы отладчик получал подтверждение завершения, используя обратный вызов [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) или [ICorDebugManagedCallback:: ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ed9a8-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed9a8-112">Этот метод не реализуется доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="ed9a8-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="ed9a8-113">Это значит, что он не реализован на <xref:System.AppDomain> уровне.</span><span class="sxs-lookup"><span data-stu-id="ed9a8-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed9a8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ed9a8-114">Requirements</span></span>  
 <span data-ttu-id="ed9a8-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed9a8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed9a8-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed9a8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed9a8-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed9a8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed9a8-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed9a8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed9a8-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ed9a8-119">See also</span></span>
