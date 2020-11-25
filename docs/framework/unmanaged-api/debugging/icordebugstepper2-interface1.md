---
title: Интерфейс ICorDebugStepper2
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
ms.openlocfilehash: ecbedfbca37a3630fc6d40c173f8a6cd05b4d3fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727644"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="ab926-102">Интерфейс ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="ab926-102">ICorDebugStepper2 Interface</span></span>

<span data-ttu-id="ab926-103">Обеспечивает поддержку отладки "только мой код" (JMC).</span><span class="sxs-lookup"><span data-stu-id="ab926-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab926-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ab926-104">Methods</span></span>  
  
|<span data-ttu-id="ab926-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ab926-105">Method</span></span>|<span data-ttu-id="ab926-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ab926-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab926-107">Метод SetJMC</span><span class="sxs-lookup"><span data-stu-id="ab926-107">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="ab926-108">Задает значение, указывающее, следует ли выполнить шаги для этого параметра ICorDebugStepper только с помощью кода, созданного разработчиком приложения.</span><span class="sxs-lookup"><span data-stu-id="ab926-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab926-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ab926-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab926-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ab926-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab926-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ab926-111">Requirements</span></span>  

 <span data-ttu-id="ab926-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab926-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab926-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab926-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab926-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab926-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab926-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab926-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab926-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ab926-116">See also</span></span>

- [<span data-ttu-id="ab926-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ab926-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
