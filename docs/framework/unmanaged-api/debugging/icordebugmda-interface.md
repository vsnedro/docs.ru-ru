---
title: Интерфейс ICorDebugMDA
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: d711f36b4e2071dac9458a023e1d3cf4743e77b3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212637"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="4fb4c-102">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="4fb4c-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="4fb4c-103">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="4fb4c-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4fb4c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4fb4c-104">Methods</span></span>  
  
|<span data-ttu-id="4fb4c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4fb4c-105">Method</span></span>|<span data-ttu-id="4fb4c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4fb4c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4fb4c-107">Метод GetDescription</span><span class="sxs-lookup"><span data-stu-id="4fb4c-107">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="4fb4c-108">Возвращает строку, содержащую описание этого MDA.</span><span class="sxs-lookup"><span data-stu-id="4fb4c-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="4fb4c-109">Метод GetFlags</span><span class="sxs-lookup"><span data-stu-id="4fb4c-109">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="4fb4c-110">Возвращает флаги, связанные с этим MDA.</span><span class="sxs-lookup"><span data-stu-id="4fb4c-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="4fb4c-111">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="4fb4c-111">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="4fb4c-112">Возвращает строку, содержащую имя этого MDA.</span><span class="sxs-lookup"><span data-stu-id="4fb4c-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="4fb4c-113">Метод GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="4fb4c-113">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="4fb4c-114">Возвращает идентификатор потока операционной системы, в котором выполняется этот MDA.</span><span class="sxs-lookup"><span data-stu-id="4fb4c-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="4fb4c-115">Метод GetXML</span><span class="sxs-lookup"><span data-stu-id="4fb4c-115">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="4fb4c-116">Возвращает полный XML-поток, связанный с этим MDA.</span><span class="sxs-lookup"><span data-stu-id="4fb4c-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fb4c-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="4fb4c-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4fb4c-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="4fb4c-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fb4c-119">Требования</span><span class="sxs-lookup"><span data-stu-id="4fb4c-119">Requirements</span></span>  
 <span data-ttu-id="4fb4c-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fb4c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fb4c-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fb4c-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fb4c-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fb4c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fb4c-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fb4c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fb4c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4fb4c-124">See also</span></span>

- [<span data-ttu-id="4fb4c-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4fb4c-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4fb4c-126">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="4fb4c-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
