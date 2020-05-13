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
ms.openlocfilehash: 6c6ff428e378e973d8846674ffacdcd04b2dbdbc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378349"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="95c57-102">Интерфейс ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="95c57-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="95c57-103">Предоставляет методы, управляющие значением, которое является ссылкой на объект.</span><span class="sxs-lookup"><span data-stu-id="95c57-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="95c57-104">(Т. е. Этот интерфейс предоставляет методы, управляющие указателем.) Этот интерфейс реализует "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="95c57-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95c57-105">Методы</span><span class="sxs-lookup"><span data-stu-id="95c57-105">Methods</span></span>  
  
|<span data-ttu-id="95c57-106">Метод</span><span class="sxs-lookup"><span data-stu-id="95c57-106">Method</span></span>|<span data-ttu-id="95c57-107">Описание</span><span class="sxs-lookup"><span data-stu-id="95c57-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95c57-108">Метод Dereference</span><span class="sxs-lookup"><span data-stu-id="95c57-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="95c57-109">Возвращает объект, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="95c57-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="95c57-110">Метод DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="95c57-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="95c57-111">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="95c57-111">Not implemented.</span></span> <span data-ttu-id="95c57-112">Этот метод не следует вызывать.</span><span class="sxs-lookup"><span data-stu-id="95c57-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="95c57-113">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="95c57-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="95c57-114">Возвращает текущий адрес памяти объекта, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="95c57-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="95c57-115">Метод IsNull</span><span class="sxs-lookup"><span data-stu-id="95c57-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="95c57-116">Возвращает значение, указывающее, является ли `ICorDebugReferenceValue` значение значением NULL, в этом случае, не `ICorDebugReferenceValue` указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="95c57-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="95c57-117">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="95c57-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="95c57-118">Задает текущий адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="95c57-118">Sets the current memory address.</span></span> <span data-ttu-id="95c57-119">Это значит, что этот метод задает `ICorDebugReferenceValue` значение, которое указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="95c57-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95c57-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="95c57-120">Remarks</span></span>  
 <span data-ttu-id="95c57-121">Среда CLR может выполнять сборку мусора для объектов при продолжении отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="95c57-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="95c57-122">Сборка мусора может перемещать объекты в памяти.</span><span class="sxs-lookup"><span data-stu-id="95c57-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="95c57-123">Либо взаимодействуют `ICorDebugReferenceValue` со сборкой мусора, так что ее сведения обновляются после сборки мусора, или же она становится неявной до сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="95c57-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="95c57-124">`ICorDebugReferenceValue`После продолжения отлаживаемого процесса объект может быть неявно недействительным.</span><span class="sxs-lookup"><span data-stu-id="95c57-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="95c57-125">Производный "ICorDebugHandleValue" не является недействительным до тех пор, пока он не будет явно освобожден или открыт.</span><span class="sxs-lookup"><span data-stu-id="95c57-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95c57-126">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="95c57-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c57-127">Требования</span><span class="sxs-lookup"><span data-stu-id="95c57-127">Requirements</span></span>  
 <span data-ttu-id="95c57-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95c57-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95c57-129">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95c57-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95c57-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95c57-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95c57-131">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95c57-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c57-132">См. также</span><span class="sxs-lookup"><span data-stu-id="95c57-132">See also</span></span>

- [<span data-ttu-id="95c57-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="95c57-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
