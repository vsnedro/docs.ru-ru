---
title: Структура COR_HEAPINFO
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
ms.openlocfilehash: 5400350e1c489ec4c2ff3cddf83a4f1a8a0c7947
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726604"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="d5e80-102">Структура COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="d5e80-102">COR_HEAPINFO Structure</span></span>

<span data-ttu-id="d5e80-103">Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.</span><span class="sxs-lookup"><span data-stu-id="d5e80-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5e80-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d5e80-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d5e80-105">Members</span></span>  
  
|<span data-ttu-id="d5e80-106">Член</span><span class="sxs-lookup"><span data-stu-id="d5e80-106">Member</span></span>|<span data-ttu-id="d5e80-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d5e80-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="d5e80-108">`true` значение, если структуры сборки мусора являются допустимыми и можно перечислить в куче. в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="d5e80-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="d5e80-109">Размер указателей в байтах в целевой архитектуре.</span><span class="sxs-lookup"><span data-stu-id="d5e80-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="d5e80-110">Количество куч логической сборки мусора в процессе.</span><span class="sxs-lookup"><span data-stu-id="d5e80-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="d5e80-111">`TRUE` Если включена одновременная (фоновая) сборка мусора; в противном случае — `FALSE` .</span><span class="sxs-lookup"><span data-stu-id="d5e80-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="d5e80-112">Член перечисления [CorDebugGCType](cordebuggctype-enumeration.md) , указывающий, работает ли сборщик мусора на рабочей станции или сервере.</span><span class="sxs-lookup"><span data-stu-id="d5e80-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5e80-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d5e80-113">Remarks</span></span>  

 <span data-ttu-id="d5e80-114">Экземпляр `COR_HEAPINFO` структуры возвращается путем вызова метода [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d5e80-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="d5e80-115">Перед перечислением объектов в куче сборки мусора необходимо всегда проверять `areGCStructuresValid` поле, чтобы убедиться в том, что куча находится в перечислимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="d5e80-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="d5e80-116">Дополнительные сведения см. в описании метода [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d5e80-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5e80-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d5e80-117">Requirements</span></span>  

 <span data-ttu-id="d5e80-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5e80-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5e80-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5e80-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5e80-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5e80-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5e80-121">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5e80-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e80-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d5e80-122">See also</span></span>

- [<span data-ttu-id="d5e80-123">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="d5e80-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="d5e80-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="d5e80-124">Debugging</span></span>](index.md)
