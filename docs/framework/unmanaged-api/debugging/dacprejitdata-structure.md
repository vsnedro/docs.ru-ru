---
title: Структура DacpReJitData
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 46708acc77dad00727ee35e7d06e4228eacbd502
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723042"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="c9c8b-102">Структура DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="c9c8b-102">DacpReJitData Structure</span></span>

<span data-ttu-id="c9c8b-103">Определяет основные сведения о конкретном инструментированном методе профилирования.</span><span class="sxs-lookup"><span data-stu-id="c9c8b-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c9c8b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9c8b-104">Syntax</span></span>

```cpp
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a><span data-ttu-id="c9c8b-105">Члены</span><span class="sxs-lookup"><span data-stu-id="c9c8b-105">Members</span></span>

| <span data-ttu-id="c9c8b-106">Член</span><span class="sxs-lookup"><span data-stu-id="c9c8b-106">Member</span></span>           | <span data-ttu-id="c9c8b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c9c8b-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="c9c8b-108">Номер редакции ReJit для метода.</span><span class="sxs-lookup"><span data-stu-id="c9c8b-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="c9c8b-109">Флаг, указывающий текущее состояние инструментирования ReJit метода для данной версии.</span><span class="sxs-lookup"><span data-stu-id="c9c8b-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="c9c8b-110">Базовый адрес реализации режиттед метода.</span><span class="sxs-lookup"><span data-stu-id="c9c8b-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="c9c8b-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c9c8b-111">Remarks</span></span>

<span data-ttu-id="c9c8b-112">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="c9c8b-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c9c8b-113">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="c9c8b-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="c9c8b-114">Структура также должна быть определена с помощью `ms_struct` упаковки, если не используется компиляторы Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c9c8b-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="c9c8b-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c9c8b-115">Requirements</span></span>

<span data-ttu-id="c9c8b-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9c8b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c9c8b-117">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="c9c8b-117">**Header:** None</span></span>  
<span data-ttu-id="c9c8b-118">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="c9c8b-118">**Library:** None</span></span>  
<span data-ttu-id="c9c8b-119">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c9c8b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c9c8b-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c9c8b-120">See also</span></span>

- [<span data-ttu-id="c9c8b-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="c9c8b-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="c9c8b-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="c9c8b-122">Debugging Structures</span></span>](debugging-structures.md)
