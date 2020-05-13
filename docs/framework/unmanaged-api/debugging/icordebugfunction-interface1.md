---
title: Интерфейс ICorDebugFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
ms.openlocfilehash: 6b7b6969c1f207decbf47217e98b7fee3aa9ce54
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213248"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="a8668-102">Интерфейс ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="a8668-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="a8668-103">Представляет управляемую функцию или метод.</span><span class="sxs-lookup"><span data-stu-id="a8668-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8668-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a8668-104">Methods</span></span>  
  
|<span data-ttu-id="a8668-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a8668-105">Method</span></span>|<span data-ttu-id="a8668-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a8668-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8668-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a8668-107">CreateBreakpoint Method</span></span>](icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="a8668-108">Создает точку останова в начале этой функции.</span><span class="sxs-lookup"><span data-stu-id="a8668-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="a8668-109">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="a8668-109">GetClass Method</span></span>](icordebugfunction-getclass-method.md)|<span data-ttu-id="a8668-110">Возвращает объект ICorDebugClass, представляющий класс, членом которого является эта функция.</span><span class="sxs-lookup"><span data-stu-id="a8668-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="a8668-111">Метод GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="a8668-111">GetCurrentVersionNumber Method</span></span>](icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="a8668-112">Возвращает номер версии последнего изменения, внесенного в эту функцию.</span><span class="sxs-lookup"><span data-stu-id="a8668-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="a8668-113">Метод GetILCode</span><span class="sxs-lookup"><span data-stu-id="a8668-113">GetILCode Method</span></span>](icordebugfunction-getilcode-method.md)|<span data-ttu-id="a8668-114">Возвращает код MSIL для этой функции.</span><span class="sxs-lookup"><span data-stu-id="a8668-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="a8668-115">Метод GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="a8668-115">GetLocalVarSigToken Method</span></span>](icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="a8668-116">Возвращает маркер метаданных для сигнатуры локальной переменной функции, представленной этим `ICorDebugFunction` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="a8668-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="a8668-117">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="a8668-117">GetModule Method</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="a8668-118">Возвращает модуль, в котором определена эта функция.</span><span class="sxs-lookup"><span data-stu-id="a8668-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="a8668-119">Метод GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="a8668-119">GetNativeCode Method</span></span>](icordebugfunction-getnativecode-method.md)|<span data-ttu-id="a8668-120">Получает машинный код для этой функции.</span><span class="sxs-lookup"><span data-stu-id="a8668-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="a8668-121">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="a8668-121">GetToken Method</span></span>](icordebugfunction-gettoken-method.md)|<span data-ttu-id="a8668-122">Возвращает маркер метаданных для этой функции.</span><span class="sxs-lookup"><span data-stu-id="a8668-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8668-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="a8668-123">Remarks</span></span>  
 <span data-ttu-id="a8668-124">`ICorDebugFunction`Интерфейс не представляет функцию с параметрами универсального типа.</span><span class="sxs-lookup"><span data-stu-id="a8668-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="a8668-125">Например, `ICorDebugFunction` экземпляр будет представлять, `Func<T>` но не `Func<string>` .</span><span class="sxs-lookup"><span data-stu-id="a8668-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="a8668-126">Вызовите метод [ICorDebugILFrame2:: енумератетипепараметерс](icordebugilframe2-enumeratetypeparameters-method.md) , чтобы получить параметры универсального типа.</span><span class="sxs-lookup"><span data-stu-id="a8668-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="a8668-127">Связь между маркером метаданных метода, `mdMethodDef` и `ICorDebugFunction` объектом метода зависит от того, разрешена ли функция "изменить и продолжить" для функции:</span><span class="sxs-lookup"><span data-stu-id="a8668-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="a8668-128">Если функция "изменить и продолжить" не разрешена для функции, между `ICorDebugFunction` объектом и токеном существует связь "один к одному" `mdMethodDef` .</span><span class="sxs-lookup"><span data-stu-id="a8668-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="a8668-129">То есть функция имеет один `ICorDebugFunction` объект и один `mdMethodDef` токен.</span><span class="sxs-lookup"><span data-stu-id="a8668-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="a8668-130">Если для функции разрешен режим "изменить и продолжить", между `ICorDebugFunction` объектом и токеном существует связь "многие к одному" `mdMethodDef` .</span><span class="sxs-lookup"><span data-stu-id="a8668-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="a8668-131">Это значит, что функция может иметь много экземпляров `ICorDebugFunction` , по одной для каждой версии функции, но только один `mdMethodDef` токен.</span><span class="sxs-lookup"><span data-stu-id="a8668-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8668-132">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a8668-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8668-133">Требования</span><span class="sxs-lookup"><span data-stu-id="a8668-133">Requirements</span></span>  
 <span data-ttu-id="a8668-134">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8668-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8668-135">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8668-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8668-136">**Библиотека:**  Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="a8668-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8668-137">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8668-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8668-138">См. также</span><span class="sxs-lookup"><span data-stu-id="a8668-138">See also</span></span>

- [<span data-ttu-id="a8668-139">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a8668-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
