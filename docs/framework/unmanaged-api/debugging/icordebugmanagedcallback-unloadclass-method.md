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
ms.openlocfilehash: 6efd451c6895e8fef443e2e86afa6e98279c6493
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724004"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="ac4e4-102">Метод ICorDebugManagedCallback::UnloadClass</span><span class="sxs-lookup"><span data-stu-id="ac4e4-102">ICorDebugManagedCallback::UnloadClass Method</span></span>

<span data-ttu-id="ac4e4-103">Уведомляет отладчик о выгрузке класса.</span><span class="sxs-lookup"><span data-stu-id="ac4e4-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac4e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac4e4-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac4e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac4e4-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="ac4e4-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий класс.</span><span class="sxs-lookup"><span data-stu-id="ac4e4-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="ac4e4-107">окне Указатель на объект ICorDebugClass, представляющий класс.</span><span class="sxs-lookup"><span data-stu-id="ac4e4-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac4e4-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ac4e4-108">Remarks</span></span>  

 <span data-ttu-id="ac4e4-109">После этого вызова не следует ссылаться на класс.</span><span class="sxs-lookup"><span data-stu-id="ac4e4-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac4e4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ac4e4-110">Requirements</span></span>  

 <span data-ttu-id="ac4e4-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac4e4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac4e4-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac4e4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac4e4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac4e4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac4e4-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac4e4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac4e4-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ac4e4-115">See also</span></span>

- [<span data-ttu-id="ac4e4-116">Метод LoadClass</span><span class="sxs-lookup"><span data-stu-id="ac4e4-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="ac4e4-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="ac4e4-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
