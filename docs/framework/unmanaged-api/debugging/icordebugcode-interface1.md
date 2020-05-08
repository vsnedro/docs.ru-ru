---
title: Интерфейс ICorDebugCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
ms.openlocfilehash: 3736627e7f42ad9db6699c31a0a618e993eef770
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893472"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="70263-102">Интерфейс ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="70263-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="70263-103">Представляет сегмент кода на языке MSIL или сегмент машинного кода.</span><span class="sxs-lookup"><span data-stu-id="70263-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70263-104">Методы</span><span class="sxs-lookup"><span data-stu-id="70263-104">Methods</span></span>  
  
|<span data-ttu-id="70263-105">Метод</span><span class="sxs-lookup"><span data-stu-id="70263-105">Method</span></span>|<span data-ttu-id="70263-106">Описание</span><span class="sxs-lookup"><span data-stu-id="70263-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70263-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="70263-107">CreateBreakpoint Method</span></span>](icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="70263-108">Создает точку останова по указанному смещению.</span><span class="sxs-lookup"><span data-stu-id="70263-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="70263-109">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="70263-109">GetAddress Method</span></span>](icordebugcode-getaddress-method.md)|<span data-ttu-id="70263-110">Возвращает относительный виртуальный адрес (RVA) сегмента кода, который представляет `ICorDebugCode` этот объект.</span><span class="sxs-lookup"><span data-stu-id="70263-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="70263-111">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="70263-111">GetCode Method</span></span>](icordebugcode-getcode-method.md)|<span data-ttu-id="70263-112">Возвращает весь код для указанной функции, отформатированный для дизассемблирования.</span><span class="sxs-lookup"><span data-stu-id="70263-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="70263-113">Этот метод не рекомендуется к использованию. Вместо этого используйте [ICorDebugCode2:: жеткодечункс](icordebugcode2-getcodechunks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="70263-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="70263-114">Метод GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="70263-114">GetEnCRemapSequencePoints Method</span></span>](icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="70263-115">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="70263-115">Not implemented.</span></span>|  
|[<span data-ttu-id="70263-116">Метод GetFunction</span><span class="sxs-lookup"><span data-stu-id="70263-116">GetFunction Method</span></span>](icordebugcode-getfunction-method.md)|<span data-ttu-id="70263-117">Возвращает "ICorDebugFunction", связанный с этим `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="70263-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="70263-118">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="70263-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="70263-119">Возвращает массив экземпляров "COR_DEBUG_IL_TO_NATIVE_MAP", которые представляют сопоставления от смещений MSIL до собственных смещений.</span><span class="sxs-lookup"><span data-stu-id="70263-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="70263-120">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="70263-120">GetSize Method</span></span>](icordebugcode-getsize-method.md)|<span data-ttu-id="70263-121">Возвращает размер двоичного кода, представленного этим `ICorDebugCode`объектом, в байтах.</span><span class="sxs-lookup"><span data-stu-id="70263-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="70263-122">Метод GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="70263-122">GetVersionNumber Method</span></span>](icordebugcode-getversionnumber-method.md)|<span data-ttu-id="70263-123">Возвращает номер, отсчитываемый от единицы, определяющий версию кода, который представляет данный `ICorDebugCode` объект.</span><span class="sxs-lookup"><span data-stu-id="70263-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="70263-124">Метод IsIL</span><span class="sxs-lookup"><span data-stu-id="70263-124">IsIL Method</span></span>](icordebugcode-isil-method.md)|<span data-ttu-id="70263-125">Возвращает значение, указывающее, компилируется `ICorDebugCode` ли это в MSIL.</span><span class="sxs-lookup"><span data-stu-id="70263-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70263-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="70263-126">Remarks</span></span>  
 <span data-ttu-id="70263-127">`ICorDebugCode`может представлять язык MSIL или машинный код.</span><span class="sxs-lookup"><span data-stu-id="70263-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="70263-128">Объект "ICorDebugFunction", представляющий код MSIL, может быть связан с нулем или `ICorDebugCode` с одним объектом.</span><span class="sxs-lookup"><span data-stu-id="70263-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="70263-129">Объект "ICorDebugFunction", представляющий машинный код, может иметь любое количество `ICorDebugCode` связанных с ним объектов.</span><span class="sxs-lookup"><span data-stu-id="70263-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70263-130">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="70263-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70263-131">Требования</span><span class="sxs-lookup"><span data-stu-id="70263-131">Requirements</span></span>  
 <span data-ttu-id="70263-132">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70263-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70263-133">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70263-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70263-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70263-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70263-135">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70263-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70263-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="70263-136">See also</span></span>

- [<span data-ttu-id="70263-137">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="70263-137">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="70263-138">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="70263-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
