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
ms.openlocfilehash: b7e738f06f9a9a06caedec2bdd0de4ab57f6d9b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719727"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="02cfd-102">Интерфейс ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="02cfd-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="02cfd-103">Представляет внутренний кадр среды выполнения в стеке.</span><span class="sxs-lookup"><span data-stu-id="02cfd-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="02cfd-104">Этот интерфейс является подклассом интерфейса ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="02cfd-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02cfd-105">Методы</span><span class="sxs-lookup"><span data-stu-id="02cfd-105">Methods</span></span>  
  
|<span data-ttu-id="02cfd-106">Метод</span><span class="sxs-lookup"><span data-stu-id="02cfd-106">Method</span></span>|<span data-ttu-id="02cfd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="02cfd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02cfd-108">Метод GetFrameType</span><span class="sxs-lookup"><span data-stu-id="02cfd-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="02cfd-109">Возвращает тип этого внутреннего кадра.</span><span class="sxs-lookup"><span data-stu-id="02cfd-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02cfd-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="02cfd-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02cfd-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="02cfd-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02cfd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="02cfd-112">Requirements</span></span>  

 <span data-ttu-id="02cfd-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02cfd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02cfd-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02cfd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02cfd-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02cfd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02cfd-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02cfd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02cfd-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="02cfd-117">See also</span></span>

- [<span data-ttu-id="02cfd-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="02cfd-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
