---
title: 'ICorDebugProcess4: метод:P Роцессстатечанжед'
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 910c411d2c63ce2c6cf262e28e08546657dc2a4c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213573"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="41b3a-102">ICorDebugProcess4: метод:P Роцессстатечанжед</span><span class="sxs-lookup"><span data-stu-id="41b3a-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="41b3a-103">Уведомляет конвейер ICorDebug о том, что отладчик out-Process продолжает выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="41b3a-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="41b3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41b3a-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="41b3a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="41b3a-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="41b3a-106">окне Член [перечисления кордебугстатечанже](cordebugstatechange-enumeration.md) , описывающий изменение в состоянии выполнения процесса.</span><span class="sxs-lookup"><span data-stu-id="41b3a-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="41b3a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="41b3a-107">Remarks</span></span>

<span data-ttu-id="41b3a-108">Предоставленный метод является частью `ICorDebugProcess4` интерфейса и соответствует четвертому слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="41b3a-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="41b3a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="41b3a-109">Requirements</span></span>

 <span data-ttu-id="41b3a-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41b3a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="41b3a-111">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="41b3a-111">**Header:** None</span></span>

 <span data-ttu-id="41b3a-112">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="41b3a-112">**Library:** None</span></span>

 <span data-ttu-id="41b3a-113">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41b3a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="41b3a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="41b3a-114">See also</span></span>

- [<span data-ttu-id="41b3a-115">Интерфейс ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="41b3a-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="41b3a-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="41b3a-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="41b3a-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="41b3a-117">Debugging</span></span>](index.md)
