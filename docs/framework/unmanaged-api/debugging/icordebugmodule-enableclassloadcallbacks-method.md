---
title: Метод ICorDebugModule::EnableClassLoadCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
ms.openlocfilehash: 1f6c6ae3b7cb45b049d0fb0d88bbf89121bccfd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710419"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="ccdbf-102">Метод ICorDebugModule::EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="ccdbf-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>

<span data-ttu-id="ccdbf-103">Определяет, вызываются ли для этого модуля обратные вызовы [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](icordebugmanagedcallback-unloadclass-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ccdbf-103">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccdbf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccdbf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccdbf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ccdbf-105">Parameters</span></span>  

 `bClassLoadCallbacks`  
 <span data-ttu-id="ccdbf-106">окне Задайте это значение `true` , чтобы среда CLR вызывала `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` методы и при возникновении связанных с ними событий.</span><span class="sxs-lookup"><span data-stu-id="ccdbf-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="ccdbf-107">Значение по умолчанию — `false` для модулей, не являющихся динамическими.</span><span class="sxs-lookup"><span data-stu-id="ccdbf-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="ccdbf-108">Значение всегда используется `true` для динамических модулей и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="ccdbf-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccdbf-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ccdbf-109">Remarks</span></span>  

 <span data-ttu-id="ccdbf-110">`ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` Обратные вызовы и всегда включены для динамических модулей и не могут быть отключены.</span><span class="sxs-lookup"><span data-stu-id="ccdbf-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccdbf-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ccdbf-111">Requirements</span></span>  

 <span data-ttu-id="ccdbf-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccdbf-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccdbf-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ccdbf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ccdbf-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccdbf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccdbf-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccdbf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccdbf-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ccdbf-116">See also</span></span>
