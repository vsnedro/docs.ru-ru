---
title: Метод ICorDebugProcess5::EnumerateGCReferences
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: 0f2f5acfc6a23398b15af3a63345050eb0dfd5b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687194"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="1b8d5-102">Метод ICorDebugProcess5::EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="1b8d5-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>

<span data-ttu-id="1b8d5-103">Возвращает перечислитель для всех объектов, которые должны быть собраны в процессе сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="1b8d5-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b8d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b8d5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b8d5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b8d5-105">Parameters</span></span>  

 `enumerateWeakReferences`  
 <span data-ttu-id="1b8d5-106">окне Логическое значение, указывающее, будут ли также перечисляться слабые ссылки.</span><span class="sxs-lookup"><span data-stu-id="1b8d5-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="1b8d5-107">Если `enumerateWeakReferences` имеет значение `true` , `ppEnum` перечислитель включает как строгие ссылки, так и слабые ссылки.</span><span class="sxs-lookup"><span data-stu-id="1b8d5-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="1b8d5-108">Если `enumerateWeakReferences` имеет значение `false` , перечислитель включает только строгие ссылки.</span><span class="sxs-lookup"><span data-stu-id="1b8d5-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="1b8d5-109">заполняет Указатель на адрес [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) , который является перечислителем для объектов, которые должны быть собраны в мусор.</span><span class="sxs-lookup"><span data-stu-id="1b8d5-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b8d5-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1b8d5-110">Remarks</span></span>  

 <span data-ttu-id="1b8d5-111">Этот метод предоставляет способ определения полной цепочки корневых объектов для любого управляемого объекта в процессе и может использоваться для определения причины, по которой объект остается в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="1b8d5-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b8d5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1b8d5-112">Requirements</span></span>  

 <span data-ttu-id="1b8d5-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b8d5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b8d5-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b8d5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b8d5-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b8d5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b8d5-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b8d5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8d5-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1b8d5-117">See also</span></span>

- [<span data-ttu-id="1b8d5-118">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="1b8d5-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="1b8d5-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1b8d5-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
