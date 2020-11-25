---
title: Метод ICorDebug::SetUnmanagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: 0bce14a6853c872d27057b9fffc32b54c59abf13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723393"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="0e7ea-102">Метод ICorDebug::SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="0e7ea-102">ICorDebug::SetUnmanagedHandler Method</span></span>

<span data-ttu-id="0e7ea-103">Указывает объект обработчика событий для неуправляемых событий.</span><span class="sxs-lookup"><span data-stu-id="0e7ea-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e7ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e7ea-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e7ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e7ea-105">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="0e7ea-106">окне Указатель на объект [икордебугунманажедкаллбакк](icordebugunmanagedcallback-interface.md) , представляющий обработчик событий для неуправляемых событий.</span><span class="sxs-lookup"><span data-stu-id="0e7ea-106">[in] A pointer to an [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e7ea-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0e7ea-107">Remarks</span></span>  

 <span data-ttu-id="0e7ea-108">Объект обработчика событий для неуправляемых событий должен быть задан после вызова метода [ICorDebug:: Initialize](icordebug-initialize-method.md) и перед вызовом [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) или [ICorDebug::D ебугактивепроцесс](icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="0e7ea-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="0e7ea-109">Однако для устаревших целей не требуется задавать объект обработчика событий для неуправляемых событий до тех пор, пока не будет вызвано первое собственное событие отладки.</span><span class="sxs-lookup"><span data-stu-id="0e7ea-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="0e7ea-110">В частности, если `ICorDebug::CreateProcess` задан флаг CREATE_SUSPENDED, события отладки машинного кода не могут быть отправлены, пока основной поток не возобновит работу.</span><span class="sxs-lookup"><span data-stu-id="0e7ea-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e7ea-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0e7ea-111">Requirements</span></span>  

 <span data-ttu-id="0e7ea-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e7ea-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e7ea-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e7ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e7ea-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e7ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e7ea-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e7ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7ea-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0e7ea-116">See also</span></span>

- [<span data-ttu-id="0e7ea-117">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="0e7ea-117">ICorDebug Interface</span></span>](icordebug-interface.md)
