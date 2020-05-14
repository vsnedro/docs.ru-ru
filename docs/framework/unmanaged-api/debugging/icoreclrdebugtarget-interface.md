---
title: Интерфейс ICoreClrDebugTarget
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
ms.openlocfilehash: c44a12ef377d29e0b33b8be86aa1d8f0aa9d26bd
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397155"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="65f40-102">Интерфейс ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="65f40-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="65f40-103">Предоставляет методы, управляющие счетчиком ссылок, перечисление процессов и освобождение памяти, связанной с отладчиком, который подключен к удаленному целевому объекту Macintosh Silverlight.</span><span class="sxs-lookup"><span data-stu-id="65f40-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65f40-104">Syntax</span></span>  
  
```cpp  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="65f40-105">Методы</span><span class="sxs-lookup"><span data-stu-id="65f40-105">Methods</span></span>  
  
|<span data-ttu-id="65f40-106">Метод</span><span class="sxs-lookup"><span data-stu-id="65f40-106">Method</span></span>|<span data-ttu-id="65f40-107">Описание</span><span class="sxs-lookup"><span data-stu-id="65f40-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65f40-108">Метод ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="65f40-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="65f40-109">Перечисляет процессы, работающие на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="65f40-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="65f40-110">Метод ICoreClrDebugTarget::EnumRuntimes</span><span class="sxs-lookup"><span data-stu-id="65f40-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="65f40-111">Перечисляет общеязыковые среды выполнения (CLR) в указанном процессе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="65f40-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="65f40-112">Метод ICoreClrDebugTarget::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="65f40-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="65f40-113">Освобождает память, выделенную методами перечисления в этом классе.</span><span class="sxs-lookup"><span data-stu-id="65f40-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65f40-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="65f40-114">Remarks</span></span>  
 <span data-ttu-id="65f40-115">В настоящее время эта функция поддерживается только для отладки целевого объекта приложения на основе Silverlight, который выполняется на удаленном компьютере Macintosh.</span><span class="sxs-lookup"><span data-stu-id="65f40-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65f40-116">Требования</span><span class="sxs-lookup"><span data-stu-id="65f40-116">Requirements</span></span>  
 <span data-ttu-id="65f40-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65f40-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65f40-118">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="65f40-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="65f40-119">**Библиотека:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="65f40-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="65f40-120">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="65f40-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f40-121">См. также статью</span><span class="sxs-lookup"><span data-stu-id="65f40-121">See also</span></span>

- [<span data-ttu-id="65f40-122">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="65f40-122">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="65f40-123">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="65f40-123">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="65f40-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="65f40-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
