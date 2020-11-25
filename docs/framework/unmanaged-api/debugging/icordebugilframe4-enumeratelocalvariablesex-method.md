---
title: Метод ICorDebugILFrame4::EnumerateLocalVariablesEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
ms.openlocfilehash: 86a3b22851aa07a546cba5a0c0b69c81ec580cee
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724979"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="56f00-102">Метод ICorDebugILFrame4::EnumerateLocalVariablesEx</span><span class="sxs-lookup"><span data-stu-id="56f00-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>

<span data-ttu-id="56f00-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="56f00-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="56f00-104">Получает перечислитель для локальной переменной в кадре и может включать переменные, добавленные в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="56f00-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f00-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56f00-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56f00-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="56f00-106">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="56f00-107">окне Элемент перечисления [ILCodeKind](ilcodekind-enumeration.md) , указывающий, включены ли в кадр переменные, добавленные в инструментирование ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="56f00-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="56f00-108">заполняет Указатель на адрес объекта "ICorDebugValueEnum", который является перечислителем для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="56f00-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56f00-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="56f00-109">Remarks</span></span>  

 <span data-ttu-id="56f00-110">Этот метод аналогичен методу [енумерателокалвариаблес](icordebugilframe-enumeratelocalvariables-method.md) , за исключением того, что он дополнительно получает доступ к переменным, добавленным в инструментарий профилировщика ReJIT.</span><span class="sxs-lookup"><span data-stu-id="56f00-110">This method is similar to the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="56f00-111">Параметр `flags` в `ILCODE_ORIGINAL_IL` эквивалентен вызову [ICorDebugILFrame:: енумерателокалвариаблес](icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="56f00-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="56f00-112">Установка значения `flags` для параметра `ILCODE_REJIT_IL` позволяет отладчику получить доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="56f00-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="56f00-113">Если промежуточный язык не инструментирован, перечисление будет пустым, а метод вернет значение `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="56f00-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="56f00-114">Перечислитель может не включать все локальные переменные выполняемого метода, так как некоторые из них могут быть неактивными.</span><span class="sxs-lookup"><span data-stu-id="56f00-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56f00-115">Требования</span><span class="sxs-lookup"><span data-stu-id="56f00-115">Requirements</span></span>  

 <span data-ttu-id="56f00-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56f00-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56f00-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56f00-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56f00-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56f00-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56f00-119">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56f00-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f00-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="56f00-120">See also</span></span>

- [<span data-ttu-id="56f00-121">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="56f00-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="56f00-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="56f00-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="56f00-123">ReJIT: руководство по How-To</span><span class="sxs-lookup"><span data-stu-id="56f00-123">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
