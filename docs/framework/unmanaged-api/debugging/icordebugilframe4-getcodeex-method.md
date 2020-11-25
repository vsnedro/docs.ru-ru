---
title: Метод ICorDebugILFrame4::GetCodeEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: a88bb02626dc125c494e4bbe68bfe6ed8bfd3b7b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719649"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="e9256-102">Метод ICorDebugILFrame4::GetCodeEx</span><span class="sxs-lookup"><span data-stu-id="e9256-102">ICorDebugILFrame4::GetCodeEx Method</span></span>

<span data-ttu-id="e9256-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="e9256-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e9256-104">Получает указатель на код, который выполняется этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="e9256-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9256-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9256-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9256-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9256-106">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="e9256-107">окне Элемент перечисления [ILCodeKind](ilcodekind-enumeration.md) , указывающий, включается ли в кадр промежуточный язык (IL), определенный в запросе ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="e9256-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="e9256-108">заполняет Указатель на адрес объекта ICorDebugCode, который представляет код, который исполняется этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="e9256-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9256-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e9256-109">Remarks</span></span>  

 <span data-ttu-id="e9256-110">Этот метод аналогичен методу [ICorDebugFrame::-Code](icordebugframe-getcode-method.md) , за исключением того, что он дополнительно получает доступ к коду, определенному в запросе ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="e9256-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="e9256-111">Вызов этого метода со `flags` значением `ILCODE_ORIGINAL_IL` эквивалентен вызову метода " [.](icordebugframe-getcode-method.md)" Если метод инструментирован, его Il будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="e9256-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="e9256-112">`ILCODE_REJIT_IL` позволяет отладчику получить доступ к промежуточному языку, определенному запросом ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="e9256-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="e9256-113">Если IL не инструментирован, `ppCode` имеет **значение NULL** и метод возвращает `S_OK` .</span><span class="sxs-lookup"><span data-stu-id="e9256-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9256-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e9256-114">Requirements</span></span>  

 <span data-ttu-id="e9256-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9256-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9256-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9256-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9256-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9256-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9256-118">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9256-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9256-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e9256-119">See also</span></span>

- [<span data-ttu-id="e9256-120">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="e9256-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="e9256-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e9256-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e9256-122">ReJIT: руководство по How-To</span><span class="sxs-lookup"><span data-stu-id="e9256-122">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
