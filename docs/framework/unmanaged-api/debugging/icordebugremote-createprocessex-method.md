---
title: Метод ICorDebugRemote::CreateProcessEx
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
ms.openlocfilehash: 37bf800f27754d1bf80aece962b7cbb85b1cbedc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712187"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="a08fe-102">Метод ICorDebugRemote::CreateProcessEx</span><span class="sxs-lookup"><span data-stu-id="a08fe-102">ICorDebugRemote::CreateProcessEx Method</span></span>

<span data-ttu-id="a08fe-103">Запускает процесс на удаленном компьютере в отладчике.</span><span class="sxs-lookup"><span data-stu-id="a08fe-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a08fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a08fe-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a08fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a08fe-105">Parameters</span></span>  

 `pRemoteTarget`  
 <span data-ttu-id="a08fe-106">окне Указатель на [интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a08fe-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="a08fe-107">Используется для определения удаленного компьютера, на котором будет запущен процесс.</span><span class="sxs-lookup"><span data-stu-id="a08fe-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="a08fe-108">окне Указатель на строку, завершающуюся нулем, которая указывает модуль, выполняемый запущенным процессом.</span><span class="sxs-lookup"><span data-stu-id="a08fe-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="a08fe-109">Модуль выполняется в контексте безопасности вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="a08fe-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="a08fe-110">окне Указатель на строку, завершающуюся нулем, которая указывает командную строку, выполняемую запущенным процессом.</span><span class="sxs-lookup"><span data-stu-id="a08fe-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="a08fe-111">окне Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="a08fe-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="a08fe-112">окне Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="a08fe-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="a08fe-113">окне Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="a08fe-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="a08fe-114">окне Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="a08fe-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="a08fe-115">окне Указатель на блок среды для нового процесса.</span><span class="sxs-lookup"><span data-stu-id="a08fe-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="a08fe-116">окне Указатель на строку, завершающуюся нулем, которая указывает полный путь к текущему каталогу для процесса.</span><span class="sxs-lookup"><span data-stu-id="a08fe-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="a08fe-117">Если этот параметр имеет значение null, то новый процесс будет иметь тот же текущий диск и каталог, что и вызывающий процесс.</span><span class="sxs-lookup"><span data-stu-id="a08fe-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="a08fe-118">окне Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="a08fe-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="a08fe-119">окне Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="a08fe-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="a08fe-120">окне Не используется для удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="a08fe-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="a08fe-121">заполняет Указатель на адрес объекта "ICorDebugProcess Interface", который представляет процесс.</span><span class="sxs-lookup"><span data-stu-id="a08fe-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a08fe-122">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a08fe-122">Return Value</span></span>  

 <span data-ttu-id="a08fe-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="a08fe-123">S_OK</span></span>  
 <span data-ttu-id="a08fe-124">Процесс успешно запущен на удаленном компьютере и для отладки возвращен "Интерфейс ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="a08fe-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="a08fe-125">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="a08fe-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="a08fe-126">Не удалось запустить процесс на удаленном компьютере и вернуть для отладки "Интерфейс ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="a08fe-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a08fe-127">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a08fe-127">Remarks</span></span>  

 <span data-ttu-id="a08fe-128">Отладка в смешанном режиме не поддерживается в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="a08fe-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a08fe-129">Требования</span><span class="sxs-lookup"><span data-stu-id="a08fe-129">Requirements</span></span>  

 <span data-ttu-id="a08fe-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a08fe-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a08fe-131">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="a08fe-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a08fe-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a08fe-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a08fe-133">**.NET Framework версии:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="a08fe-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08fe-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a08fe-134">See also</span></span>

- [<span data-ttu-id="a08fe-135">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="a08fe-135">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="a08fe-136">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a08fe-136">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="a08fe-137">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a08fe-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
