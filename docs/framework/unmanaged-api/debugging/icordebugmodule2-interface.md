---
title: Интерфейс ICorDebugModule2
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: 2b8e6048dd6b8df71ac3dddcc4397f6d512127c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695885"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="d79bd-102">Интерфейс ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="d79bd-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="d79bd-103">Служит логическим расширением интерфейса ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="d79bd-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d79bd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d79bd-104">Methods</span></span>  
  
|<span data-ttu-id="d79bd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d79bd-105">Method</span></span>|<span data-ttu-id="d79bd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d79bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d79bd-107">Метод ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="d79bd-107">ApplyChanges Method</span></span>](icordebugmodule2-applychanges-method.md)|<span data-ttu-id="d79bd-108">Применяет изменения в метаданных и изменения в коде промежуточного языка MSIL к выполняющемуся процессу.</span><span class="sxs-lookup"><span data-stu-id="d79bd-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="d79bd-109">Метод GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="d79bd-109">GetJITCompilerFlags Method</span></span>](icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="d79bd-110">Возвращает флаги, управляющие JIT-компиляцией для этого `ICorDebugModule2` .</span><span class="sxs-lookup"><span data-stu-id="d79bd-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="d79bd-111">Метод ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="d79bd-111">ResolveAssembly Method</span></span>](icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="d79bd-112">Разрешает сборку, на которую ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="d79bd-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="d79bd-113">Метод SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="d79bd-113">SetJITCompilerFlags Method</span></span>](icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="d79bd-114">Задает флаги, управляющие JIT-компиляцией для этого `ICorDebugModule2` .</span><span class="sxs-lookup"><span data-stu-id="d79bd-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="d79bd-115">Метод SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="d79bd-115">SetJMCStatus Method</span></span>](icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="d79bd-116">Устанавливает состояние Только мой код (JMC) всех методов всех классов в данном `ICorDebugModule2` значении, за исключением тех, которые заданы в `pTokens` массиве, для которого задано обратное значение.</span><span class="sxs-lookup"><span data-stu-id="d79bd-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d79bd-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d79bd-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d79bd-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d79bd-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d79bd-119">Требования</span><span class="sxs-lookup"><span data-stu-id="d79bd-119">Requirements</span></span>  

 <span data-ttu-id="d79bd-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d79bd-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d79bd-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d79bd-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d79bd-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d79bd-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d79bd-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d79bd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79bd-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d79bd-124">See also</span></span>

- [<span data-ttu-id="d79bd-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d79bd-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
