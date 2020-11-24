---
title: Метод ICorDebugProcess5::GetGCHeapInformation
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
ms.openlocfilehash: 43054a71445193bae7a74e0ed6785cccd1d02dc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670996"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="f6fcd-102">Метод ICorDebugProcess5::GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="f6fcd-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>

<span data-ttu-id="f6fcd-103">Содержит общие сведения о куче сборки мусора, включая возможность перечисления в данный момент.</span><span class="sxs-lookup"><span data-stu-id="f6fcd-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6fcd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6fcd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6fcd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6fcd-105">Parameters</span></span>  

 `pHeapInfo`  
 <span data-ttu-id="f6fcd-106">заполняет Указатель на [COR_HEAPINFO](cor-heapinfo-structure.md) значение, предоставляющее общие сведения о куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f6fcd-106">[out] A pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6fcd-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f6fcd-107">Remarks</span></span>  

 <span data-ttu-id="f6fcd-108">`ICorDebugProcess5::GetGCHeapInformation`Перед перечислением областей кучи или отдельных куч необходимо вызвать метод, чтобы убедиться в том, что структуры сборки мусора в этом процессе являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="f6fcd-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="f6fcd-109">Невозможно выполнить обход кучи сборки мусора, пока выполняется сбор.</span><span class="sxs-lookup"><span data-stu-id="f6fcd-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="f6fcd-110">В противном случае перечисление может собирать недопустимые структуры сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f6fcd-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6fcd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f6fcd-111">Requirements</span></span>  

 <span data-ttu-id="f6fcd-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6fcd-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6fcd-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6fcd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6fcd-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6fcd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6fcd-115">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6fcd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6fcd-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f6fcd-116">See also</span></span>

- [<span data-ttu-id="f6fcd-117">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="f6fcd-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="f6fcd-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f6fcd-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
