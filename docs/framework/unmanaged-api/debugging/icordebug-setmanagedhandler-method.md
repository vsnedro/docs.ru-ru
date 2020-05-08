---
title: Метод ICorDebug::SetManagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: a197d260c55d24f906da7d7f2768bb7ba1ad751f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895343"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="86fbf-102">Метод ICorDebug::SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="86fbf-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="86fbf-103">Указывает объект обработчика событий для управляемых событий.</span><span class="sxs-lookup"><span data-stu-id="86fbf-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86fbf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86fbf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86fbf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86fbf-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="86fbf-106">окне Указатель на объект [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) , который является объектом обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="86fbf-106">[in] A pointer to an [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86fbf-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="86fbf-107">Remarks</span></span>  
 <span data-ttu-id="86fbf-108">`SetManagedHandler`должен вызываться во время создания.</span><span class="sxs-lookup"><span data-stu-id="86fbf-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="86fbf-109">Если `ICorDebugManagedCallback` реализация не содержит достаточных интерфейсов для работы с событиями отладки для отлаживаемого приложения, `SetManagedHandler` возвращает значение HRESULT E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="86fbf-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86fbf-110">Требования</span><span class="sxs-lookup"><span data-stu-id="86fbf-110">Requirements</span></span>  
 <span data-ttu-id="86fbf-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86fbf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86fbf-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86fbf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86fbf-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86fbf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86fbf-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86fbf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86fbf-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="86fbf-115">See also</span></span>

- [<span data-ttu-id="86fbf-116">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="86fbf-116">ICorDebug Interface</span></span>](icordebug-interface.md)
