---
title: Интерфейс ICorDebugClass
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
ms.openlocfilehash: d7417e8dc193172c77d23fe3fa72c8298d802b5c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894042"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="af793-102">Интерфейс ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="af793-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="af793-103">Представляет тип, который может быть базовым или сложным (иными словами, пользовательским).</span><span class="sxs-lookup"><span data-stu-id="af793-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="af793-104">Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="af793-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af793-105">Методы</span><span class="sxs-lookup"><span data-stu-id="af793-105">Methods</span></span>  
  
|<span data-ttu-id="af793-106">Метод</span><span class="sxs-lookup"><span data-stu-id="af793-106">Method</span></span>|<span data-ttu-id="af793-107">Описание</span><span class="sxs-lookup"><span data-stu-id="af793-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af793-108">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="af793-108">GetModule Method</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="af793-109">Возвращает модуль, который определяет этот класс.</span><span class="sxs-lookup"><span data-stu-id="af793-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="af793-110">Метод GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="af793-110">GetStaticFieldValue Method</span></span>](icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="af793-111">Возвращает значение указанного статического поля.</span><span class="sxs-lookup"><span data-stu-id="af793-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="af793-112">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="af793-112">GetToken Method</span></span>](icordebugclass-gettoken-method.md)|<span data-ttu-id="af793-113">Возвращает маркер `TypeDef` метаданных для этого класса.</span><span class="sxs-lookup"><span data-stu-id="af793-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af793-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="af793-114">Remarks</span></span>  
 <span data-ttu-id="af793-115">`ICorDebugClass` Интерфейс представляет универсальный тип, экземпляр которого не был создан.</span><span class="sxs-lookup"><span data-stu-id="af793-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="af793-116">Интерфейс ICorDebugType представляет экземпляр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="af793-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="af793-117">Например, `Hashtable<K, V>` будет представлено `ICorDebugClass`, а `Hashtable<Int32, String>` будет представлено. `ICorDebugType`</span><span class="sxs-lookup"><span data-stu-id="af793-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="af793-118">Типы, не являющиеся универсальными, представлены `ICorDebugClass` как `ICorDebugType`, так и.</span><span class="sxs-lookup"><span data-stu-id="af793-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="af793-119">Последний интерфейс появился в .NET Framework версии 2,0 для обработки создания экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="af793-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af793-120">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="af793-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af793-121">Требования</span><span class="sxs-lookup"><span data-stu-id="af793-121">Requirements</span></span>  
 <span data-ttu-id="af793-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af793-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af793-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af793-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af793-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af793-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af793-125">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af793-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af793-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="af793-126">See also</span></span>

- [<span data-ttu-id="af793-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="af793-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
