---
title: Метод ICorDebug::CanLaunchOrAttach
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
ms.openlocfilehash: 354df02b27e87550ba602fe102352455c227441b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859690"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="71ca1-102">Метод ICorDebug::CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="71ca1-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="71ca1-103">Возвращает значение HRESULT, указывающее, возможен ли запуск нового процесса или присоединение к указанному существующему процессу в контексте текущего компьютера и конфигурации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="71ca1-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71ca1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71ca1-104">Syntax</span></span>  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71ca1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="71ca1-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="71ca1-106">окне Идентификатор существующего процесса.</span><span class="sxs-lookup"><span data-stu-id="71ca1-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="71ca1-107">окне `true` Если вы планируете запустить отладку Win32 или присоединиться с включенной отладкой Win32, передавайте значение. в противном `false`случае передайте.</span><span class="sxs-lookup"><span data-stu-id="71ca1-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71ca1-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="71ca1-108">Return Value</span></span>  
 <span data-ttu-id="71ca1-109">S_OK, если службы отладки определяют, что можно запустить новый процесс или присоединиться к заданному процессу, учитывая сведения о текущем компьютере и конфигурации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="71ca1-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="71ca1-110">Возможные значения HRESULT:</span><span class="sxs-lookup"><span data-stu-id="71ca1-110">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="71ca1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="71ca1-111">S_OK</span></span>  
  
- <span data-ttu-id="71ca1-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="71ca1-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="71ca1-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="71ca1-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="71ca1-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="71ca1-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71ca1-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="71ca1-115">Remarks</span></span>  
 <span data-ttu-id="71ca1-116">Этот метод является исключительно информационным.</span><span class="sxs-lookup"><span data-stu-id="71ca1-116">This method is purely informational.</span></span> <span data-ttu-id="71ca1-117">Интерфейс не будет останавливаться при запуске или присоединении к процессу, независимо от значения, возвращаемого `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="71ca1-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="71ca1-118">Если планируется запуск с включенной отладкой Win32 или подключение с включенной отладкой `true` Win32 `win32DebuggingEnabled`, передайте.</span><span class="sxs-lookup"><span data-stu-id="71ca1-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="71ca1-119">Значение HRESULT, возвращаемое, `CanLaunchOrAttach` может отличаться при использовании этого параметра.</span><span class="sxs-lookup"><span data-stu-id="71ca1-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71ca1-120">Требования</span><span class="sxs-lookup"><span data-stu-id="71ca1-120">Requirements</span></span>  
 <span data-ttu-id="71ca1-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71ca1-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71ca1-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71ca1-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71ca1-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71ca1-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71ca1-124">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71ca1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ca1-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="71ca1-125">See also</span></span>

- [<span data-ttu-id="71ca1-126">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="71ca1-126">ICorDebug Interface</span></span>](icordebug-interface.md)
