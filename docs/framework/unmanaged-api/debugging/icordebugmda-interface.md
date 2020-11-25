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
ms.openlocfilehash: c4ff28ff1019b5314902a4e71f6d02b5a2fd8d70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710848"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="ae9df-102">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="ae9df-102">ICorDebugMDA Interface</span></span>

<span data-ttu-id="ae9df-103">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="ae9df-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae9df-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ae9df-104">Methods</span></span>  
  
|<span data-ttu-id="ae9df-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ae9df-105">Method</span></span>|<span data-ttu-id="ae9df-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ae9df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae9df-107">Метод GetDescription</span><span class="sxs-lookup"><span data-stu-id="ae9df-107">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="ae9df-108">Возвращает строку, содержащую описание этого MDA.</span><span class="sxs-lookup"><span data-stu-id="ae9df-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="ae9df-109">Метод GetFlags</span><span class="sxs-lookup"><span data-stu-id="ae9df-109">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="ae9df-110">Возвращает флаги, связанные с этим MDA.</span><span class="sxs-lookup"><span data-stu-id="ae9df-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="ae9df-111">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="ae9df-111">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="ae9df-112">Возвращает строку, содержащую имя этого MDA.</span><span class="sxs-lookup"><span data-stu-id="ae9df-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="ae9df-113">Метод GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="ae9df-113">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="ae9df-114">Возвращает идентификатор потока операционной системы, в котором выполняется этот MDA.</span><span class="sxs-lookup"><span data-stu-id="ae9df-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="ae9df-115">Метод GetXML</span><span class="sxs-lookup"><span data-stu-id="ae9df-115">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="ae9df-116">Возвращает полный XML-поток, связанный с этим MDA.</span><span class="sxs-lookup"><span data-stu-id="ae9df-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae9df-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ae9df-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae9df-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ae9df-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae9df-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ae9df-119">Requirements</span></span>  

 <span data-ttu-id="ae9df-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae9df-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae9df-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae9df-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae9df-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae9df-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae9df-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae9df-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9df-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ae9df-124">See also</span></span>

- [<span data-ttu-id="ae9df-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ae9df-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ae9df-126">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="ae9df-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
