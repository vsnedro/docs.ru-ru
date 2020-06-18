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
ms.openlocfilehash: 3d4e44eefaf99a40b9c4f1c45e7dd81192f8b607
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904277"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="9a4ac-102">Метод ICorDebugHeapSegmentEnum::Next</span><span class="sxs-lookup"><span data-stu-id="9a4ac-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="9a4ac-103">Возвращает указанное число экземпляров [COR_SEGMENT](cor-segment-structure.md) , содержащих сведения о регионах памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="9a4ac-103">Gets the specified number of [COR_SEGMENT](cor-segment-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a4ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a4ac-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a4ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a4ac-105">Parameters</span></span>  
 <span data-ttu-id="9a4ac-106">celt</span><span class="sxs-lookup"><span data-stu-id="9a4ac-106">celt</span></span>  
 <span data-ttu-id="9a4ac-107">окне Число извлекаемых сегментов.</span><span class="sxs-lookup"><span data-stu-id="9a4ac-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="9a4ac-108">сегменты</span><span class="sxs-lookup"><span data-stu-id="9a4ac-108">segments</span></span>  
 <span data-ttu-id="9a4ac-109">заполняет Массив указателей, каждый из которых указывает на объект [COR_SEGMENT](cor-segment-structure.md) , который предоставляет сведения о области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="9a4ac-109">[out] An array of pointers, each of which points to a [COR_SEGMENT](cor-segment-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="9a4ac-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="9a4ac-110">pceltFetched</span></span>  
 <span data-ttu-id="9a4ac-111">заполняет Указатель на число объектов [COR_SEGMENT](cor-segment-structure.md) , фактически возвращаемых в `segments` .</span><span class="sxs-lookup"><span data-stu-id="9a4ac-111">[out] A pointer to the number of [COR_SEGMENT](cor-segment-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="9a4ac-112">Это значение может быть `null`, если параметр `celt` имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="9a4ac-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a4ac-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a4ac-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a4ac-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9a4ac-114">Requirements</span></span>  
 <span data-ttu-id="9a4ac-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a4ac-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a4ac-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a4ac-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a4ac-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a4ac-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a4ac-118">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a4ac-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a4ac-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9a4ac-119">See also</span></span>

- [<span data-ttu-id="9a4ac-120">Интерфейс ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="9a4ac-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="9a4ac-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9a4ac-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
