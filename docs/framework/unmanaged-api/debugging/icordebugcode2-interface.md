---
title: Интерфейс ICorDebugCode2
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
ms.openlocfilehash: 39767ea2603018d088aaefc5da32879aaf49fee6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893489"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="4e40a-102">Интерфейс ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="4e40a-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="4e40a-103">Предоставляет методы, расширяющие возможности "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="4e40a-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e40a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4e40a-104">Methods</span></span>  
  
|<span data-ttu-id="4e40a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4e40a-105">Method</span></span>|<span data-ttu-id="4e40a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4e40a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e40a-107">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="4e40a-107">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="4e40a-108">Возвращает фрагменты кода, из которого состоит этот объект кода.</span><span class="sxs-lookup"><span data-stu-id="4e40a-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="4e40a-109">Метод GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="4e40a-109">GetCompilerFlags Method</span></span>](icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="4e40a-110">Возвращает флаги, указывающие условия, при которых этот объект кода был либо JIT-скомпилирован, либо создан с помощью генератора образов в машинном коде (Ngen. exe).</span><span class="sxs-lookup"><span data-stu-id="4e40a-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e40a-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="4e40a-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e40a-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="4e40a-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e40a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4e40a-113">Requirements</span></span>  
 <span data-ttu-id="4e40a-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e40a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e40a-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e40a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e40a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e40a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e40a-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e40a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e40a-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4e40a-118">See also</span></span>

- [<span data-ttu-id="4e40a-119">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="4e40a-119">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="4e40a-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4e40a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
