---
title: Перечисление CorDebugStateChange
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
ms.openlocfilehash: d94422d25da91cd2a6653a95cbd852c3930a151a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795694"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="d09e7-102">Перечисление CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="d09e7-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="d09e7-103">Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.</span><span class="sxs-lookup"><span data-stu-id="d09e7-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="d09e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d09e7-104">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="d09e7-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d09e7-105">Members</span></span>

| <span data-ttu-id="d09e7-106">Участник</span><span class="sxs-lookup"><span data-stu-id="d09e7-106">Member</span></span>            | <span data-ttu-id="d09e7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d09e7-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="d09e7-108">Процесс достиг нового состояния памяти с помощью механизма прямого выполнения.</span><span class="sxs-lookup"><span data-stu-id="d09e7-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="d09e7-109">Память процесса может отличаться произвольным образом от предыдущего варианта.</span><span class="sxs-lookup"><span data-stu-id="d09e7-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d09e7-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d09e7-110">Remarks</span></span>

 <span data-ttu-id="d09e7-111">Член `CorDebugStateChange` перечисления предоставляется в качестве аргумента, когда отладчик вызывает `ProcessStateChanged` метод с помощью [ICorDebugProcess4::P Роцессстатечанжед](icordebugprocess4-processstatechanged-method.md) или [ICorDebugProcess6::P роцессстатечанжед](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="d09e7-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="d09e7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d09e7-112">Requirements</span></span>

 <span data-ttu-id="d09e7-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d09e7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="d09e7-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d09e7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="d09e7-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d09e7-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="d09e7-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d09e7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d09e7-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d09e7-117">See also</span></span>

- [<span data-ttu-id="d09e7-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="d09e7-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="d09e7-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="d09e7-119">Debugging</span></span>](index.md)
