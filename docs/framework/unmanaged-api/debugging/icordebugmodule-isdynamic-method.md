---
title: Метод ICorDebugModule::IsDynamic
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
ms.openlocfilehash: 4517f266bbb500223214a6a8fe5881e8b29566c3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206888"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="b1eb4-102">Метод ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="b1eb4-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="b1eb4-103">Возвращает значение, указывающее, является ли этот модуль динамическим.</span><span class="sxs-lookup"><span data-stu-id="b1eb4-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1eb4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1eb4-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1eb4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1eb4-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="b1eb4-106">[out] `true` значение, если этот модуль является динамическим; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="b1eb4-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1eb4-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1eb4-107">Remarks</span></span>  
 <span data-ttu-id="b1eb4-108">Динамический модуль может добавлять новые классы и удалять существующие классы даже после загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="b1eb4-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="b1eb4-109">Обратные вызовы [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](icordebugmanagedcallback-unloadclass-method.md) информируют отладчик о добавлении или удалении класса.</span><span class="sxs-lookup"><span data-stu-id="b1eb4-109">The [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1eb4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b1eb4-110">Requirements</span></span>  
 <span data-ttu-id="b1eb4-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1eb4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1eb4-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1eb4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1eb4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1eb4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1eb4-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1eb4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
