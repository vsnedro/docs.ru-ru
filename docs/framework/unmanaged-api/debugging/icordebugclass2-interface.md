---
title: Интерфейс ICorDebugClass2
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: ce3f289ae914817071fad5274c45d1e5fae71a06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717985"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="1179c-102">Интерфейс ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="1179c-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="1179c-103">Представляет универсальный класс или класс параметром метода типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="1179c-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="1179c-104">Этот интерфейс расширяет [ICorDebugClass](icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1179c-104">This interface extends [ICorDebugClass](icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1179c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="1179c-105">Methods</span></span>  
  
|<span data-ttu-id="1179c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="1179c-106">Method</span></span>|<span data-ttu-id="1179c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1179c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1179c-108">Метод GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="1179c-108">GetParameterizedType Method</span></span>](icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="1179c-109">Возвращает объявление типа для этого класса.</span><span class="sxs-lookup"><span data-stu-id="1179c-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="1179c-110">Метод SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="1179c-110">SetJMCStatus Method</span></span>](icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="1179c-111">Для каждого метода этого класса задает значение, указывающее, является ли метод определяемым пользователем кодом.</span><span class="sxs-lookup"><span data-stu-id="1179c-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1179c-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1179c-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1179c-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="1179c-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1179c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1179c-114">Requirements</span></span>  

 <span data-ttu-id="1179c-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1179c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1179c-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1179c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1179c-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1179c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1179c-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1179c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1179c-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1179c-119">See also</span></span>

- [<span data-ttu-id="1179c-120">Интерфейс ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="1179c-120">ICorDebugClass Interface</span></span>](icordebugclass-interface.md)
- [<span data-ttu-id="1179c-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1179c-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
