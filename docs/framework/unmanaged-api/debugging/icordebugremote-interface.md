---
title: Интерфейс ICorDebugRemote
ms.date: 03/30/2017
api_name:
- ICorDebugRemote
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemote
helpviewer_keywords:
- ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type:
- apiref
ms.openlocfilehash: 276d36c511105087190cb7e9dfeaa6932efc67ff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712109"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="80387-102">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="80387-102">ICorDebugRemote Interface</span></span>

<span data-ttu-id="80387-103">Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="80387-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80387-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80387-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="80387-105">Методы</span><span class="sxs-lookup"><span data-stu-id="80387-105">Methods</span></span>  
  
|<span data-ttu-id="80387-106">Метод</span><span class="sxs-lookup"><span data-stu-id="80387-106">Method</span></span>|<span data-ttu-id="80387-107">Описание</span><span class="sxs-lookup"><span data-stu-id="80387-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80387-108">Метод ICorDebugRemote::CreateProcessEx</span><span class="sxs-lookup"><span data-stu-id="80387-108">ICorDebugRemote::CreateProcessEx Method</span></span>](icordebugremote-createprocessex-method.md)|<span data-ttu-id="80387-109">Создает процесс на удаленном компьютере для управляемой отладки.</span><span class="sxs-lookup"><span data-stu-id="80387-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="80387-110">Метод ICorDebugRemote::DebugActiveProcessEx</span><span class="sxs-lookup"><span data-stu-id="80387-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="80387-111">Запускает процесс на удаленном компьютере в отладчике.</span><span class="sxs-lookup"><span data-stu-id="80387-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80387-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="80387-112">Remarks</span></span>  

 <span data-ttu-id="80387-113">В настоящее время эта функция поддерживается только для отладки целевого объекта приложения на основе Silverlight, который выполняется на удаленном компьютере Macintosh.</span><span class="sxs-lookup"><span data-stu-id="80387-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80387-114">Требования</span><span class="sxs-lookup"><span data-stu-id="80387-114">Requirements</span></span>  

 <span data-ttu-id="80387-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80387-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80387-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80387-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80387-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80387-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80387-118">**.NET Framework версии:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="80387-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80387-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="80387-119">See also</span></span>

- [<span data-ttu-id="80387-120">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="80387-120">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="80387-121">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="80387-121">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="80387-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="80387-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
