---
title: Интерфейс ICorDebugInternalFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
ms.openlocfilehash: a17c46d5ef08963bb0d7fc280ba8b90531e41c5b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719636"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="898ba-102">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="898ba-102">ICorDebugInternalFrame2 Interface</span></span>

<span data-ttu-id="898ba-103">Предоставляет сведения о внутренних кадрах, включая стековый адрес и положение относительно объектов ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="898ba-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="898ba-104">Методы</span><span class="sxs-lookup"><span data-stu-id="898ba-104">Methods</span></span>  
  
|<span data-ttu-id="898ba-105">Метод</span><span class="sxs-lookup"><span data-stu-id="898ba-105">Method</span></span>|<span data-ttu-id="898ba-106">Описание</span><span class="sxs-lookup"><span data-stu-id="898ba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="898ba-107">Метод GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="898ba-107">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="898ba-108">Возвращает адрес стека внутреннего кадра.</span><span class="sxs-lookup"><span data-stu-id="898ba-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="898ba-109">Метод IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="898ba-109">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="898ba-110">Проверяет, `this` находится ли внутренний кадр ближе к конечному объекту, чем указанный объект ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="898ba-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="898ba-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="898ba-111">Remarks</span></span>  

 <span data-ttu-id="898ba-112">Этот интерфейс расширяет интерфейс ICorDebugInternalFrame.</span><span class="sxs-lookup"><span data-stu-id="898ba-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="898ba-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="898ba-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="898ba-114">Требования</span><span class="sxs-lookup"><span data-stu-id="898ba-114">Requirements</span></span>  

 <span data-ttu-id="898ba-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="898ba-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="898ba-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="898ba-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="898ba-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="898ba-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="898ba-118">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="898ba-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898ba-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="898ba-119">See also</span></span>

- [<span data-ttu-id="898ba-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="898ba-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="898ba-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="898ba-121">Debugging</span></span>](index.md)
