---
title: Метод ICorDebugHeapSegmentEnum::Next
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: c9999961ec20a31cf82d5ad60104bcdd04c340d1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210180"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="fb324-102">Метод ICorDebugHeapSegmentEnum::Next</span><span class="sxs-lookup"><span data-stu-id="fb324-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="fb324-103">Возвращает указанное число экземпляров [COR_HEAPOBJECT](cor-heapobject-structure.md) , содержащих сведения о регионах памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="fb324-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb324-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb324-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb324-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb324-105">Parameters</span></span>  
 <span data-ttu-id="fb324-106">celt</span><span class="sxs-lookup"><span data-stu-id="fb324-106">celt</span></span>  
 <span data-ttu-id="fb324-107">окне Число извлекаемых сегментов.</span><span class="sxs-lookup"><span data-stu-id="fb324-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="fb324-108">сегменты</span><span class="sxs-lookup"><span data-stu-id="fb324-108">segments</span></span>  
 <span data-ttu-id="fb324-109">заполняет Массив указателей, каждый из которых указывает на объект [COR_HEAPOBJECT](cor-heapobject-structure.md) , который предоставляет сведения о области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="fb324-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="fb324-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="fb324-110">pceltFetched</span></span>  
 <span data-ttu-id="fb324-111">заполняет Указатель на число объектов [COR_HEAPOBJECT](cor-heapobject-structure.md) , фактически возвращаемых в `segments` .</span><span class="sxs-lookup"><span data-stu-id="fb324-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="fb324-112">Это значение может быть `null`, если параметр `celt` имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="fb324-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb324-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="fb324-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb324-114">Требования</span><span class="sxs-lookup"><span data-stu-id="fb324-114">Requirements</span></span>  
 <span data-ttu-id="fb324-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb324-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb324-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb324-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb324-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb324-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb324-118">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb324-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb324-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fb324-119">See also</span></span>

- [<span data-ttu-id="fb324-120">Интерфейс ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="fb324-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="fb324-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fb324-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
