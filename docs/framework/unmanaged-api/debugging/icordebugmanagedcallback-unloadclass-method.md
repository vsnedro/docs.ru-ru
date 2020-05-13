---
title: Метод ICorDebugManagedCallback::UnloadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: a7b71170f58ddfe0295da28b8c9fc73286b074e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212273"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="018d3-102">Метод ICorDebugManagedCallback::UnloadClass</span><span class="sxs-lookup"><span data-stu-id="018d3-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="018d3-103">Уведомляет отладчик о выгрузке класса.</span><span class="sxs-lookup"><span data-stu-id="018d3-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="018d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="018d3-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="018d3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="018d3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="018d3-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий класс.</span><span class="sxs-lookup"><span data-stu-id="018d3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="018d3-107">окне Указатель на объект ICorDebugClass, представляющий класс.</span><span class="sxs-lookup"><span data-stu-id="018d3-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="018d3-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="018d3-108">Remarks</span></span>  
 <span data-ttu-id="018d3-109">После этого вызова не следует ссылаться на класс.</span><span class="sxs-lookup"><span data-stu-id="018d3-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="018d3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="018d3-110">Requirements</span></span>  
 <span data-ttu-id="018d3-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="018d3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="018d3-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="018d3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="018d3-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="018d3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="018d3-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="018d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018d3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="018d3-115">See also</span></span>

- [<span data-ttu-id="018d3-116">Метод LoadClass</span><span class="sxs-lookup"><span data-stu-id="018d3-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="018d3-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="018d3-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
