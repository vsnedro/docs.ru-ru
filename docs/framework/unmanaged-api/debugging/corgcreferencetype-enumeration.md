---
title: Перечисление CorGCReferenceType
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
ms.openlocfilehash: e2903637faa11a3c0a62080cc6fafcf1fc668a56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704998"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="175f6-102">Перечисление CorGCReferenceType</span><span class="sxs-lookup"><span data-stu-id="175f6-102">CorGCReferenceType Enumeration</span></span>

<span data-ttu-id="175f6-103">Идентифицирует источник объекта, в котором должна быть выполнена сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="175f6-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="175f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="175f6-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a><span data-ttu-id="175f6-105">Члены</span><span class="sxs-lookup"><span data-stu-id="175f6-105">Members</span></span>  
  
|<span data-ttu-id="175f6-106">Имя участника</span><span class="sxs-lookup"><span data-stu-id="175f6-106">Member name</span></span>|<span data-ttu-id="175f6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="175f6-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="175f6-108">Дескриптор строгой ссылки из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="175f6-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="175f6-109">Указатель на закрепленную строгую ссылку из таблицы обработчика объектов.</span><span class="sxs-lookup"><span data-stu-id="175f6-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="175f6-110">Указатель на слабую ссылку из таблицы обработчика объектов.</span><span class="sxs-lookup"><span data-stu-id="175f6-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="175f6-111">Указатель на слабый объект, подсчитанный по ссылке, из таблицы обработчика объектов.</span><span class="sxs-lookup"><span data-stu-id="175f6-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="175f6-112">Указатель на объект, подсчитанный по ссылке, из таблицы обработчика объектов.</span><span class="sxs-lookup"><span data-stu-id="175f6-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="175f6-113">Маркер зависимого объекта из таблицы обработчика объектов.</span><span class="sxs-lookup"><span data-stu-id="175f6-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="175f6-114">Асинхронный закрепленный объект из таблицы дескрипторов объектов.</span><span class="sxs-lookup"><span data-stu-id="175f6-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="175f6-115">Строгая ссылка, хранящая приблизительный размер общего закрытия всех объектов и корневых объектов во время сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="175f6-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="175f6-116">Ссылка из управляемого стека.</span><span class="sxs-lookup"><span data-stu-id="175f6-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="175f6-117">Ссылка из очереди метода завершения.</span><span class="sxs-lookup"><span data-stu-id="175f6-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="175f6-118">корхандлестронгонли</span><span class="sxs-lookup"><span data-stu-id="175f6-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="175f6-119">Возвращать только строгие ссылки из таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="175f6-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="175f6-120">Это значение используется только методом [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="175f6-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="175f6-121">Возвращать только слабые ссылки из таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="175f6-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="175f6-122">Это значение используется только методом [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="175f6-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="175f6-123">Возвращает все ссылки из таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="175f6-123">Return all references from the handle table.</span></span> <span data-ttu-id="175f6-124">Это значение используется только методом [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="175f6-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="175f6-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="175f6-125">Remarks</span></span>  

 <span data-ttu-id="175f6-126">`CorGCReferenceType`Перечисление используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="175f6-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
- <span data-ttu-id="175f6-127">В качестве значения `type` поля структуры [COR_GC_REFERENCE](cor-gc-reference-structure.md) указывает источник ссылки или маркера.</span><span class="sxs-lookup"><span data-stu-id="175f6-127">As the value of the `type` field of the [COR_GC_REFERENCE](cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
- <span data-ttu-id="175f6-128">В качестве `types` аргумента метода [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) указывает типы дескрипторов, включаемых в перечисление.</span><span class="sxs-lookup"><span data-stu-id="175f6-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="175f6-129">Требования</span><span class="sxs-lookup"><span data-stu-id="175f6-129">Requirements</span></span>  

 <span data-ttu-id="175f6-130">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="175f6-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="175f6-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="175f6-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="175f6-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="175f6-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="175f6-133">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="175f6-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="175f6-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="175f6-134">See also</span></span>

- [<span data-ttu-id="175f6-135">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="175f6-135">Debugging Enumerations</span></span>](debugging-enumerations.md)
