---
title: Интерфейс ICorDebugValue2
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: 7aca5fcb5a55331756b4f98c08eb46fc4db1e289
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720351"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="ec395-102">Интерфейс ICorDebugValue2</span><span class="sxs-lookup"><span data-stu-id="ec395-102">ICorDebugValue2 Interface</span></span>

<span data-ttu-id="ec395-103">Расширяет интерфейс "ICorDebugValue" для обеспечения поддержки объектов "ICorDebugType".</span><span class="sxs-lookup"><span data-stu-id="ec395-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec395-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ec395-104">Methods</span></span>  
  
|<span data-ttu-id="ec395-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ec395-105">Method</span></span>|<span data-ttu-id="ec395-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ec395-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec395-107">Метод GetExactType</span><span class="sxs-lookup"><span data-stu-id="ec395-107">GetExactType Method</span></span>](icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="ec395-108">Возвращает указатель интерфейса на `ICorDebugType` объект, представляющий <xref:System.Type> это значение.</span><span class="sxs-lookup"><span data-stu-id="ec395-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec395-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ec395-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec395-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ec395-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec395-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ec395-111">Requirements</span></span>  

 <span data-ttu-id="ec395-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec395-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec395-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec395-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec395-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec395-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec395-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec395-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec395-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ec395-116">See also</span></span>

- [<span data-ttu-id="ec395-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ec395-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

- [<span data-ttu-id="ec395-118">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="ec395-118">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
