---
title: Интерфейс ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: aa1db39b564b987fb8d0f79d529f5af59b7e4c02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713759"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="e648f-102">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="e648f-102">ICorDebugDataTarget2 Interface</span></span>

<span data-ttu-id="e648f-103">Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e648f-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e648f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e648f-104">Methods</span></span>  
  
|<span data-ttu-id="e648f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e648f-105">Method</span></span>|<span data-ttu-id="e648f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e648f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e648f-107">Метод CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="e648f-107">CreateVirtualUnwinder Method</span></span>](icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="e648f-108">Создает новый элемент очистки стека, запускающий операцию очистки, начиная с исходного контекста (который не обязательно является концом потока).</span><span class="sxs-lookup"><span data-stu-id="e648f-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="e648f-109">Метод EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="e648f-109">EnumerateThreadIDs Method</span></span>](icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="e648f-110">Возвращает список идентификаторов активных потоков.</span><span class="sxs-lookup"><span data-stu-id="e648f-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="e648f-111">Метод GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="e648f-111">GetImageFromPointer Method</span></span>](icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="e648f-112">Возвращает базовый адрес и размер модуля из адреса в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="e648f-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="e648f-113">Метод GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="e648f-113">GetImageLocation Method</span></span>](icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="e648f-114">Возвращает путь для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="e648f-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="e648f-115">Метод GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="e648f-115">GetSymbolProviderForImage Method</span></span>](icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="e648f-116">Возвращает поставщика символов для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="e648f-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e648f-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e648f-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e648f-118">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e648f-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e648f-119">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e648f-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e648f-120">Требования</span><span class="sxs-lookup"><span data-stu-id="e648f-120">Requirements</span></span>  

 <span data-ttu-id="e648f-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e648f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e648f-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e648f-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e648f-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e648f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e648f-124">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e648f-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e648f-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e648f-125">See also</span></span>

- [<span data-ttu-id="e648f-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e648f-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e648f-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="e648f-127">Debugging</span></span>](index.md)
