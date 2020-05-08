---
title: Интерфейс ICorDebugBlockingObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: 8be4332da77c3fbf4229a3fbeb9ba835a7a13eee
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894797"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="54e0f-102">Интерфейс ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="54e0f-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="54e0f-103">Предоставляет перечислитель для списка структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="54e0f-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="54e0f-104">Этот интерфейс является подклассом интерфейса ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="54e0f-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54e0f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="54e0f-105">Methods</span></span>  
  
|<span data-ttu-id="54e0f-106">Метод</span><span class="sxs-lookup"><span data-stu-id="54e0f-106">Method</span></span>|<span data-ttu-id="54e0f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="54e0f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="54e0f-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="54e0f-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="54e0f-109">Перечисляет по списку структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="54e0f-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54e0f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="54e0f-110">Remarks</span></span>  
 <span data-ttu-id="54e0f-111">Каждая структура `CorDebugBlockingObject` представляет объект, блокирующий поток.</span><span class="sxs-lookup"><span data-stu-id="54e0f-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54e0f-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="54e0f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54e0f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="54e0f-113">Requirements</span></span>  
 <span data-ttu-id="54e0f-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54e0f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54e0f-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54e0f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54e0f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54e0f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54e0f-117">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e0f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e0f-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="54e0f-118">See also</span></span>

- [<span data-ttu-id="54e0f-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="54e0f-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="54e0f-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="54e0f-120">Debugging</span></span>](index.md)
