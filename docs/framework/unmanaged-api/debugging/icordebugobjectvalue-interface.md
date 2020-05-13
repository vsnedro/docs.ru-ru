---
title: Интерфейс ICorDebugObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: 603ab20b57dc4ba736b0342797d0be649a5bebc4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207483"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="95d20-102">Интерфейс ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="95d20-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="95d20-103">Подкласс "ICorDebugValue", представляющий значение, которое содержит объект.</span><span class="sxs-lookup"><span data-stu-id="95d20-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95d20-104">Методы</span><span class="sxs-lookup"><span data-stu-id="95d20-104">Methods</span></span>  
  
|<span data-ttu-id="95d20-105">Метод</span><span class="sxs-lookup"><span data-stu-id="95d20-105">Method</span></span>|<span data-ttu-id="95d20-106">Описание</span><span class="sxs-lookup"><span data-stu-id="95d20-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95d20-107">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="95d20-107">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="95d20-108">Возвращает указатель интерфейса на общеязыковую среду выполнения (CLR) <xref:System.Type> объекта, `ICorDebugObjectValue` на который ссылается эта ссылка.</span><span class="sxs-lookup"><span data-stu-id="95d20-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="95d20-109">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="95d20-109">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="95d20-110">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="95d20-110">Not implemented.</span></span>|  
|[<span data-ttu-id="95d20-111">Метод GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="95d20-111">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="95d20-112">Возвращает указатель интерфейса на объект [ICorDebugValue](icordebugvalue-interface.md) , представляющий значение указанного поля указанного класса.</span><span class="sxs-lookup"><span data-stu-id="95d20-112">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="95d20-113">Метод GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="95d20-113">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="95d20-114">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="95d20-114">Obsolete.</span></span> <span data-ttu-id="95d20-115">Этот метод не следует вызывать.</span><span class="sxs-lookup"><span data-stu-id="95d20-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="95d20-116">Метод GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="95d20-116">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="95d20-117">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="95d20-117">Not implemented.</span></span>|  
|[<span data-ttu-id="95d20-118">Метод IsValueClass</span><span class="sxs-lookup"><span data-stu-id="95d20-118">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="95d20-119">Возвращает значение, указывающее, является ли объект, на который ссылается это, `ICorDebugObjectValue` типом значения.</span><span class="sxs-lookup"><span data-stu-id="95d20-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="95d20-120">Метод SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="95d20-120">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="95d20-121">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="95d20-121">Obsolete.</span></span> <span data-ttu-id="95d20-122">Этот метод не следует вызывать.</span><span class="sxs-lookup"><span data-stu-id="95d20-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95d20-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="95d20-123">Remarks</span></span>  
 <span data-ttu-id="95d20-124">`ICorDebugObjectValue`Остается действительным до тех пор, пока отлаживаемый процесс не будет продолжен.</span><span class="sxs-lookup"><span data-stu-id="95d20-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95d20-125">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="95d20-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95d20-126">Требования</span><span class="sxs-lookup"><span data-stu-id="95d20-126">Requirements</span></span>  
 <span data-ttu-id="95d20-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95d20-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95d20-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95d20-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95d20-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95d20-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95d20-130">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95d20-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d20-131">См. также</span><span class="sxs-lookup"><span data-stu-id="95d20-131">See also</span></span>

- [<span data-ttu-id="95d20-132">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="95d20-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
