---
title: Интерфейс ICorDebugChainEnum
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum
helpviewer_keywords:
- ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6639335c-48e1-4e74-a4f3-70a6a0f54af1
topic_type:
- apiref
ms.openlocfilehash: dd2507bb66e036dfbb1f4e8cc262f01d926adca1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728229"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="a8019-102">Интерфейс ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="a8019-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="a8019-103">Реализует методы ICorDebugEnum и перечисляет ICorDebugChain массивы.</span><span class="sxs-lookup"><span data-stu-id="a8019-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8019-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a8019-104">Methods</span></span>  
  
|<span data-ttu-id="a8019-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a8019-105">Method</span></span>|<span data-ttu-id="a8019-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a8019-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8019-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="a8019-107">Next Method</span></span>](icordebugchainenum-next-method.md)|<span data-ttu-id="a8019-108">Возвращает указанное количество `ICorDebugChain` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="a8019-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8019-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a8019-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8019-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a8019-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8019-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a8019-111">Requirements</span></span>  

 <span data-ttu-id="a8019-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8019-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8019-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8019-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8019-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8019-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8019-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8019-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8019-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a8019-116">See also</span></span>

- [<span data-ttu-id="a8019-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a8019-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
