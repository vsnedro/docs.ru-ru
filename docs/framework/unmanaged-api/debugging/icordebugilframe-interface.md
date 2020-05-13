---
title: Интерфейс ICorDebugILFrame
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 1f1e42cd929d2d6282d282cf62dce00104b3a925
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210245"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="5aaa9-102">Интерфейс ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="5aaa9-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="5aaa9-103">Представляет кадр стека кода промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="5aaa9-104">Этот интерфейс является подклассом интерфейса ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5aaa9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5aaa9-105">Methods</span></span>  
  
|<span data-ttu-id="5aaa9-106">Метод</span><span class="sxs-lookup"><span data-stu-id="5aaa9-106">Method</span></span>|<span data-ttu-id="5aaa9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5aaa9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5aaa9-108">Метод CanSetIP</span><span class="sxs-lookup"><span data-stu-id="5aaa9-108">CanSetIP Method</span></span>](icordebugilframe-cansetip-method.md)|<span data-ttu-id="5aaa9-109">Возвращает значение, указывающее, можно ли задать для указателя инструкции заданное расположение смещения.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="5aaa9-110">Метод EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="5aaa9-110">EnumerateArguments Method</span></span>](icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="5aaa9-111">Возвращает перечислитель для аргументов в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="5aaa9-112">Метод EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="5aaa9-112">EnumerateLocalVariables Method</span></span>](icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="5aaa9-113">Возвращает перечислитель для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="5aaa9-114">Метод GetArgument</span><span class="sxs-lookup"><span data-stu-id="5aaa9-114">GetArgument Method</span></span>](icordebugilframe-getargument-method.md)|<span data-ttu-id="5aaa9-115">Возвращает значение указанного аргумента в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="5aaa9-116">Метод GetIP</span><span class="sxs-lookup"><span data-stu-id="5aaa9-116">GetIP Method</span></span>](icordebugilframe-getip-method.md)|<span data-ttu-id="5aaa9-117">Возвращает значение указателя инструкции и битовое значение сочетания, которое описывает, как было получено значение указателя инструкции.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="5aaa9-118">Метод GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="5aaa9-118">GetLocalVariable Method</span></span>](icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="5aaa9-119">Возвращает значение указанной локальной переменной в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="5aaa9-120">Метод GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="5aaa9-120">GetStackDepth Method</span></span>](icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="5aaa9-121">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-121">Not implemented.</span></span>|  
|[<span data-ttu-id="5aaa9-122">Метод GetStackValue</span><span class="sxs-lookup"><span data-stu-id="5aaa9-122">GetStackValue Method</span></span>](icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="5aaa9-123">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-123">Not implemented.</span></span>|  
|[<span data-ttu-id="5aaa9-124">Метод SetIP</span><span class="sxs-lookup"><span data-stu-id="5aaa9-124">SetIP Method</span></span>](icordebugilframe-setip-method.md)|<span data-ttu-id="5aaa9-125">Устанавливает указатель инструкции на указанное положение смещения в коде MSIL.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5aaa9-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="5aaa9-126">Remarks</span></span>  
 <span data-ttu-id="5aaa9-127">`ICorDebugILFrame`Интерфейс является специализированным интерфейсом ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="5aaa9-128">Он используется либо для кадров кода MSIL, либо для кадров, скомпилированных JIT.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="5aaa9-129">JIT-скомпилированные кадры реализуют `ICorDebugILFrame` интерфейс и интерфейс ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5aaa9-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="5aaa9-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aaa9-131">Требования</span><span class="sxs-lookup"><span data-stu-id="5aaa9-131">Requirements</span></span>  
 <span data-ttu-id="5aaa9-132">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5aaa9-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5aaa9-133">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5aaa9-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5aaa9-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5aaa9-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5aaa9-135">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5aaa9-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aaa9-136">См. также</span><span class="sxs-lookup"><span data-stu-id="5aaa9-136">See also</span></span>

- [<span data-ttu-id="5aaa9-137">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5aaa9-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
