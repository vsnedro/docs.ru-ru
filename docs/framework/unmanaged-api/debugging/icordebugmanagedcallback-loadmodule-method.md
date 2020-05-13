---
title: Метод ICorDebugManagedCallback::LoadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: cd4a16bc8b48f147ed03555b51eee5f42a445bc6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212706"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="75006-102">Метод ICorDebugManagedCallback::LoadModule</span><span class="sxs-lookup"><span data-stu-id="75006-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="75006-103">Уведомляет отладчик о том, что модуль среды CLR успешно загружен.</span><span class="sxs-lookup"><span data-stu-id="75006-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75006-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75006-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75006-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="75006-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="75006-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в который был загружен модуль.</span><span class="sxs-lookup"><span data-stu-id="75006-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="75006-107">окне Указатель на объект ICorDebugModule, представляющий модуль CLR.</span><span class="sxs-lookup"><span data-stu-id="75006-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75006-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="75006-108">Remarks</span></span>  
 <span data-ttu-id="75006-109">`LoadModule`Обратный вызов предоставляет подходящее время для проверки метаданных модуля, установки флагов JIT-компилятора или включения или отключения обратных вызовов при загрузке класса для модуля.</span><span class="sxs-lookup"><span data-stu-id="75006-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75006-110">Требования</span><span class="sxs-lookup"><span data-stu-id="75006-110">Requirements</span></span>  
 <span data-ttu-id="75006-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75006-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75006-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75006-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75006-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75006-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75006-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75006-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75006-115">См. также</span><span class="sxs-lookup"><span data-stu-id="75006-115">See also</span></span>

- [<span data-ttu-id="75006-116">Метод UnloadModule</span><span class="sxs-lookup"><span data-stu-id="75006-116">UnloadModule Method</span></span>](icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="75006-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="75006-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
