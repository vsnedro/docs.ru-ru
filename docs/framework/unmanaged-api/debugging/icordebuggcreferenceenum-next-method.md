---
title: Метод ICorDebugGCReferenceEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: 1cf6f9c5fe8777f3333e449a804a3c3a0a64ff19
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213092"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="84119-102">Метод ICorDebugGCReferenceEnum::Next</span><span class="sxs-lookup"><span data-stu-id="84119-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="84119-103">Возвращает указанное число экземпляров [COR_GC_REFERENCE](cor-gc-reference-structure.md) , содержащих сведения об объектах, которые будут собираться сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="84119-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84119-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84119-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84119-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84119-105">Parameters</span></span>  
 <span data-ttu-id="84119-106">celt</span><span class="sxs-lookup"><span data-stu-id="84119-106">celt</span></span>  
 <span data-ttu-id="84119-107">окне Число извлекаемых корневых элементов.</span><span class="sxs-lookup"><span data-stu-id="84119-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="84119-108">корня</span><span class="sxs-lookup"><span data-stu-id="84119-108">roots</span></span>  
 <span data-ttu-id="84119-109">заполняет Массив указателей, каждый из которых указывает на объект [COR_GC_REFERENCE](cor-gc-reference-structure.md) , представляющий корень объекта, который должен быть собран сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="84119-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="84119-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="84119-110">pceltFetched</span></span>  
 <span data-ttu-id="84119-111">заполняет Указатель на число объектов [COR_GC_REFERENCE](cor-gc-reference-structure.md) , фактически возвращаемых в `roots` .</span><span class="sxs-lookup"><span data-stu-id="84119-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="84119-112">Это значение может быть `null`, если параметр `celt` имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="84119-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84119-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="84119-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84119-114">Требования</span><span class="sxs-lookup"><span data-stu-id="84119-114">Requirements</span></span>  
 <span data-ttu-id="84119-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84119-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84119-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84119-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84119-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84119-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84119-118">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84119-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84119-119">См. также</span><span class="sxs-lookup"><span data-stu-id="84119-119">See also</span></span>

- [<span data-ttu-id="84119-120">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="84119-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="84119-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="84119-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
