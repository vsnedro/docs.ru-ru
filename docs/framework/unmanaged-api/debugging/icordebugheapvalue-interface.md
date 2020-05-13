---
title: Интерфейс ICorDebugHeapValue
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
ms.openlocfilehash: 36a485413490045ca49b99fca4fe5d43edc37114
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213014"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="76bc6-102">Интерфейс ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="76bc6-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="76bc6-103">Подкласс "ICorDebugValue", представляющий объект, собранный сборщиком мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="76bc6-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76bc6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="76bc6-104">Methods</span></span>  
  
|<span data-ttu-id="76bc6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="76bc6-105">Method</span></span>|<span data-ttu-id="76bc6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="76bc6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76bc6-107">Метод CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="76bc6-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="76bc6-108">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="76bc6-108">Not implemented.</span></span>|  
|[<span data-ttu-id="76bc6-109">Метод IsValid</span><span class="sxs-lookup"><span data-stu-id="76bc6-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="76bc6-110">Возвращает значение, указывающее, является ли объект, представленный этим объектом `ICorDebugHeapValue` , допустимым или освобожденным сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="76bc6-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="76bc6-111">Этот метод не рекомендуется к использованию в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="76bc6-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76bc6-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="76bc6-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76bc6-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="76bc6-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76bc6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="76bc6-114">Requirements</span></span>  
 <span data-ttu-id="76bc6-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76bc6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76bc6-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76bc6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76bc6-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76bc6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76bc6-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76bc6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76bc6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="76bc6-119">See also</span></span>

- [<span data-ttu-id="76bc6-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="76bc6-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
