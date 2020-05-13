---
title: Метод ICorDebugRemote::DebugActiveProcessEx
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
ms.openlocfilehash: b95e9f3a0d584511a2bcf156ed2c50a98f96d071
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379064"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="fc2ac-102">Метод ICorDebugRemote::DebugActiveProcessEx</span><span class="sxs-lookup"><span data-stu-id="fc2ac-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="fc2ac-103">Запускает процесс на удаленном компьютере в отладчике.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc2ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc2ac-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc2ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc2ac-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="fc2ac-106">окне Указатель на [интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="fc2ac-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="fc2ac-107">Этот параметр используется для определения компьютера, на котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="fc2ac-108">окне Идентификатор процесса, к которому должен быть присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="fc2ac-109">[входные] `true` значение, если отладчик должен вести себя в качестве отладчика Win32 для процесса и передавать неуправляемые обратные вызовы; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="fc2ac-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="fc2ac-110">заполняет Указатель на адрес объекта "ICorDebugProcess", который представляет процесс, к которому присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc2ac-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fc2ac-111">Return Value</span></span>  
 <span data-ttu-id="fc2ac-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc2ac-112">S_OK</span></span>  
 <span data-ttu-id="fc2ac-113">Успешно присоединен к процессу на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="fc2ac-114">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="fc2ac-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="fc2ac-115">Не удалось присоединиться к процессу на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc2ac-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc2ac-116">Remarks</span></span>  
 <span data-ttu-id="fc2ac-117">Отладка в смешанном режиме не поддерживается в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc2ac-118">Требования</span><span class="sxs-lookup"><span data-stu-id="fc2ac-118">Requirements</span></span>  
 <span data-ttu-id="fc2ac-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc2ac-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc2ac-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc2ac-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc2ac-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc2ac-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc2ac-122">**.NET Framework версии:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="fc2ac-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc2ac-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fc2ac-123">See also</span></span>

- [<span data-ttu-id="fc2ac-124">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="fc2ac-124">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="fc2ac-125">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="fc2ac-125">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="fc2ac-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fc2ac-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
