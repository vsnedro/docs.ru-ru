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
ms.openlocfilehash: ee3ea319360bba1a113c15daf8cf143ea512e5cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733325"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="e81e3-102">Интерфейс ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="e81e3-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="e81e3-103">Подкласс "ICorDebugValue", представляющий объект, собранный сборщиком мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e81e3-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e81e3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e81e3-104">Methods</span></span>  
  
|<span data-ttu-id="e81e3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e81e3-105">Method</span></span>|<span data-ttu-id="e81e3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e81e3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e81e3-107">Метод CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e81e3-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="e81e3-108">Не реализован.</span><span class="sxs-lookup"><span data-stu-id="e81e3-108">Not implemented.</span></span>|  
|[<span data-ttu-id="e81e3-109">Метод IsValid</span><span class="sxs-lookup"><span data-stu-id="e81e3-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="e81e3-110">Возвращает значение, указывающее, является ли объект, представленный этим объектом `ICorDebugHeapValue` , допустимым или освобожденным сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="e81e3-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="e81e3-111">Этот метод не рекомендуется к использованию в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="e81e3-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e81e3-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e81e3-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e81e3-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="e81e3-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e81e3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e81e3-114">Requirements</span></span>  

 <span data-ttu-id="e81e3-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e81e3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e81e3-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e81e3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e81e3-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e81e3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e81e3-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e81e3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81e3-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e81e3-119">See also</span></span>

- [<span data-ttu-id="e81e3-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e81e3-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
