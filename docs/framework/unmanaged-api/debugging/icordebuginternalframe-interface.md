---
title: Интерфейс ICorDebugInternalFrame
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
ms.openlocfilehash: 332bc99795c0a4c896b60c61941a5a24b3f4accc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209960"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="fa1e2-102">Интерфейс ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="fa1e2-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="fa1e2-103">Представляет внутренний кадр среды выполнения в стеке.</span><span class="sxs-lookup"><span data-stu-id="fa1e2-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="fa1e2-104">Этот интерфейс является подклассом интерфейса ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="fa1e2-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa1e2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fa1e2-105">Methods</span></span>  
  
|<span data-ttu-id="fa1e2-106">Метод</span><span class="sxs-lookup"><span data-stu-id="fa1e2-106">Method</span></span>|<span data-ttu-id="fa1e2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fa1e2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa1e2-108">Метод GetFrameType</span><span class="sxs-lookup"><span data-stu-id="fa1e2-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="fa1e2-109">Возвращает тип этого внутреннего кадра.</span><span class="sxs-lookup"><span data-stu-id="fa1e2-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa1e2-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa1e2-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa1e2-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="fa1e2-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa1e2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fa1e2-112">Requirements</span></span>  
 <span data-ttu-id="fa1e2-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa1e2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa1e2-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa1e2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa1e2-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa1e2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa1e2-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa1e2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa1e2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fa1e2-117">See also</span></span>

- [<span data-ttu-id="fa1e2-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fa1e2-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
