---
title: Интерфейс ICorDebugReferenceValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
ms.openlocfilehash: 343e504e086e740236d7b5977452cc0d789883fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728411"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="ffc1f-102">Интерфейс ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="ffc1f-102">ICorDebugReferenceValue Interface</span></span>

<span data-ttu-id="ffc1f-103">Предоставляет методы, управляющие значением, которое является ссылкой на объект.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="ffc1f-104">(Т. е. Этот интерфейс предоставляет методы, управляющие указателем.) Этот интерфейс реализует "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="ffc1f-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffc1f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ffc1f-105">Methods</span></span>  
  
|<span data-ttu-id="ffc1f-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ffc1f-106">Method</span></span>|<span data-ttu-id="ffc1f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ffc1f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffc1f-108">Метод Dereference</span><span class="sxs-lookup"><span data-stu-id="ffc1f-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="ffc1f-109">Возвращает объект, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="ffc1f-110">Метод DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="ffc1f-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="ffc1f-111">Не реализован.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-111">Not implemented.</span></span> <span data-ttu-id="ffc1f-112">Этот метод не следует вызывать.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="ffc1f-113">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="ffc1f-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="ffc1f-114">Возвращает текущий адрес памяти объекта, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="ffc1f-115">Метод IsNull</span><span class="sxs-lookup"><span data-stu-id="ffc1f-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="ffc1f-116">Возвращает значение, указывающее, является ли `ICorDebugReferenceValue` значение значением NULL, в этом случае, не `ICorDebugReferenceValue` указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="ffc1f-117">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="ffc1f-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="ffc1f-118">Задает текущий адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-118">Sets the current memory address.</span></span> <span data-ttu-id="ffc1f-119">Это значит, что этот метод задает `ICorDebugReferenceValue` значение, которое указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffc1f-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ffc1f-120">Remarks</span></span>  

 <span data-ttu-id="ffc1f-121">Среда CLR может выполнять сборку мусора для объектов при продолжении отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="ffc1f-122">Сборка мусора может перемещать объекты в памяти.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="ffc1f-123">Либо взаимодействуют `ICorDebugReferenceValue` со сборкой мусора, так что ее сведения обновляются после сборки мусора, или же она становится неявной до сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="ffc1f-124">`ICorDebugReferenceValue`После продолжения отлаживаемого процесса объект может быть неявно недействительным.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="ffc1f-125">Производный "ICorDebugHandleValue" не является недействительным до тех пор, пока он не будет явно освобожден или открыт.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ffc1f-126">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ffc1f-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffc1f-127">Требования</span><span class="sxs-lookup"><span data-stu-id="ffc1f-127">Requirements</span></span>  

 <span data-ttu-id="ffc1f-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffc1f-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffc1f-129">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffc1f-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffc1f-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffc1f-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffc1f-131">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffc1f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc1f-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ffc1f-132">See also</span></span>

- [<span data-ttu-id="ffc1f-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ffc1f-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
