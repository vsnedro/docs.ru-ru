---
title: Метод ICorDebugManagedCallback::UnloadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: 07996a78d7f559de587c8a3eb2babfc06675169d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212650"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="f13e7-102">Метод ICorDebugManagedCallback::UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="f13e7-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="f13e7-103">Уведомляет отладчик о том, что сборка среды CLR была выгружена.</span><span class="sxs-lookup"><span data-stu-id="f13e7-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f13e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f13e7-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f13e7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f13e7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f13e7-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий сборку.</span><span class="sxs-lookup"><span data-stu-id="f13e7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="f13e7-107">окне Указатель на объект ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="f13e7-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f13e7-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f13e7-108">Remarks</span></span>  
 <span data-ttu-id="f13e7-109">Сборка не должна использоваться после этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f13e7-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f13e7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f13e7-110">Requirements</span></span>  
 <span data-ttu-id="f13e7-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f13e7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f13e7-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f13e7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f13e7-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f13e7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f13e7-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f13e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f13e7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f13e7-115">See also</span></span>

- [<span data-ttu-id="f13e7-116">Метод LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="f13e7-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="f13e7-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="f13e7-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
