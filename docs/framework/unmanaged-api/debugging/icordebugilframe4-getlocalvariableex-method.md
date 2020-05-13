---
title: Метод ICorDebugILFrame4::GetLocalVariableEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: 8d6ef550309ea7f8bae616a5f7e5c41b4f07374a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213729"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="9e0e8-102">Метод ICorDebugILFrame4::GetLocalVariableEx</span><span class="sxs-lookup"><span data-stu-id="9e0e8-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="9e0e8-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="9e0e8-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="9e0e8-104">Получает значение указанной локальной переменной в этом кадре стека промежуточного языка (IL) и дополнительно получает доступ к переменной, добавленной в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="9e0e8-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e0e8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e0e8-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,
   [in] DWORD dwIndex,
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e0e8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e0e8-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="9e0e8-107">окне Элемент перечисления [ILCodeKind](ilcodekind-enumeration.md) , указывающий, включается ли переменная, добавленная в инструментирование профилировщика ReJIT, в кадр.</span><span class="sxs-lookup"><span data-stu-id="9e0e8-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="9e0e8-108">[в] Индекс локальной переменной в кадре стека промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="9e0e8-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9e0e8-109">заполняет Указатель на адрес объекта ICorDebugValue, который представляет извлеченное значение.</span><span class="sxs-lookup"><span data-stu-id="9e0e8-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e0e8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e0e8-110">Remarks</span></span>  
 <span data-ttu-id="9e0e8-111">Этот метод аналогичен методу [жетлокалвариабле](icordebugilframe-getlocalvariable-method.md) , за исключением того, что он дополнительно получает доступ к переменной, добавленной в инструментарий профилировщика ReJIT.</span><span class="sxs-lookup"><span data-stu-id="9e0e8-111">This method is similar to the [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="9e0e8-112">Вызов этого метода со `flags` значением `ILCODE_ORIGINAL_IL` эквивалентен вызову [жетлокалвариабле](icordebugilframe-getlocalvariable-method.md); если метод оснащен дополнительными локальными переменными, доступ к этим переменным невозможен.</span><span class="sxs-lookup"><span data-stu-id="9e0e8-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="9e0e8-113">`ILCODE_REJIT_IL` обеспечивает отладчику доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="9e0e8-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="9e0e8-114">Если промежуточный язык не инструментирован, метод возвращает значение `E_INVALIDARG`.</span><span class="sxs-lookup"><span data-stu-id="9e0e8-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e0e8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="9e0e8-115">Requirements</span></span>  
 <span data-ttu-id="9e0e8-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e0e8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e0e8-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e0e8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e0e8-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e0e8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e0e8-119">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e0e8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e0e8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9e0e8-120">See also</span></span>

- [<span data-ttu-id="9e0e8-121">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="9e0e8-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="9e0e8-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9e0e8-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9e0e8-123">ReJIT: руководство</span><span class="sxs-lookup"><span data-stu-id="9e0e8-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
