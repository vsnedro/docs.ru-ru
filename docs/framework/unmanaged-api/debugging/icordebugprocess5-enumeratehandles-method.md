---
title: Метод ICorDebugProcess5::EnumerateHandles
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
ms.openlocfilehash: 291b384d6f0c8c1404b380c653693ec65fcfc960
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213417"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="e2149-102">Метод ICorDebugProcess5::EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="e2149-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="e2149-103">Возвращает перечислитель для дескрипторов объектов в процессе.</span><span class="sxs-lookup"><span data-stu-id="e2149-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2149-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2149-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2149-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2149-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="e2149-106">окне Побитовое сочетание значений [CorGCReferenceType](corgcreferencetype-enumeration.md) , определяющих тип дескрипторов, включаемых в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="e2149-106">[in] A bitwise combination of [CorGCReferenceType](corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="e2149-107">заполняет Указатель на адрес [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) , который является перечислителем для объектов, которые должны быть собраны в мусор.</span><span class="sxs-lookup"><span data-stu-id="e2149-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2149-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="e2149-108">Remarks</span></span>  
 <span data-ttu-id="e2149-109">`EnumerateHandles`— Это вспомогательная функция, которая поддерживает проверку таблицы Handle.</span><span class="sxs-lookup"><span data-stu-id="e2149-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="e2149-110">Он похож на метод [метод ICorDebugProcess5:: енумератегкреференцес](icordebugprocess5-enumerategcreferences-method.md) , за исключением того, что вместо заполнения коллекции [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) всеми объектами, которые должны быть собраны сборщиком мусора, он включает только объекты, имеющие дескрипторы из таблицы дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="e2149-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="e2149-111">`types`Параметр задает типы обработчиков для включения в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="e2149-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="e2149-112">`types`может быть любым из следующих трех членов перечисления [CorGCReferenceType](corgcreferencetype-enumeration.md) :</span><span class="sxs-lookup"><span data-stu-id="e2149-112">`types` can be any of the following three members of the [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="e2149-113">`CorHandleStrongOnly`(обрабатывает только строгие ссылки).</span><span class="sxs-lookup"><span data-stu-id="e2149-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="e2149-114">`CorHandleWeakOnly`(дескрипторы только для слабых ссылок).</span><span class="sxs-lookup"><span data-stu-id="e2149-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="e2149-115">`CorHandleAll`(все дескрипторы).</span><span class="sxs-lookup"><span data-stu-id="e2149-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2149-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e2149-116">Requirements</span></span>  
 <span data-ttu-id="e2149-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2149-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2149-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2149-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2149-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2149-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2149-120">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2149-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2149-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e2149-121">See also</span></span>

- [<span data-ttu-id="e2149-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="e2149-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="e2149-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="e2149-123">Debugging</span></span>](index.md)
