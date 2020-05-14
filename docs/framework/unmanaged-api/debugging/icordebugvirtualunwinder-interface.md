---
title: Интерфейс ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 59ecf3da4b44af7b04dec26fbc3ea182c185d04a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396451"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="af747-102">Интерфейс ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="af747-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="af747-103">Предоставляет методы, помогающие очистить стек.</span><span class="sxs-lookup"><span data-stu-id="af747-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af747-104">Методы</span><span class="sxs-lookup"><span data-stu-id="af747-104">Methods</span></span>  
  
|<span data-ttu-id="af747-105">Метод</span><span class="sxs-lookup"><span data-stu-id="af747-105">Method</span></span>|<span data-ttu-id="af747-106">Имя</span><span class="sxs-lookup"><span data-stu-id="af747-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="af747-107">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="af747-107">GetContext Method</span></span>](icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="af747-108">Получает текущий контекст этого средства очистки.</span><span class="sxs-lookup"><span data-stu-id="af747-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="af747-109">Метод Next</span><span class="sxs-lookup"><span data-stu-id="af747-109">Next Method</span></span>](icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="af747-110">Переходит в контекст вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="af747-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af747-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="af747-111">Remarks</span></span>  
 <span data-ttu-id="af747-112">Элементы интерфейса `ICorDebugVirtualUnwinder` реализуются отладчиком для упрощения очистки стека.</span><span class="sxs-lookup"><span data-stu-id="af747-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af747-113">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="af747-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="af747-114">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="af747-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af747-115">Требования</span><span class="sxs-lookup"><span data-stu-id="af747-115">Requirements</span></span>  
 <span data-ttu-id="af747-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af747-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af747-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af747-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af747-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af747-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af747-119">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af747-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af747-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="af747-120">See also</span></span>

- [<span data-ttu-id="af747-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="af747-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="af747-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="af747-122">Debugging</span></span>](index.md)
