---
title: Интерфейс ICorDebugAppDomain2
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
ms.openlocfilehash: 1643d91f373ff233540026440ee21aa4c146f3e3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895133"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="d15be-102">Интерфейс ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="d15be-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="d15be-103">Предоставляет методы для работы с массивами, указателями, указателями функций и ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="d15be-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="d15be-104">Этот интерфейс является расширением интерфейса ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="d15be-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d15be-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d15be-105">Methods</span></span>  
  
|<span data-ttu-id="d15be-106">Метод</span><span class="sxs-lookup"><span data-stu-id="d15be-106">Method</span></span>|<span data-ttu-id="d15be-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d15be-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d15be-108">Метод GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="d15be-108">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="d15be-109">Возвращает массив указанного типа или указатель или ссылку на указанный тип.</span><span class="sxs-lookup"><span data-stu-id="d15be-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="d15be-110">Метод GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="d15be-110">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="d15be-111">Возвращает указатель на функцию с заданной сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="d15be-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d15be-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="d15be-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d15be-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d15be-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d15be-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d15be-114">Requirements</span></span>  
 <span data-ttu-id="d15be-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d15be-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d15be-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d15be-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d15be-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d15be-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d15be-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d15be-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d15be-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d15be-119">See also</span></span>

- [<span data-ttu-id="d15be-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d15be-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
