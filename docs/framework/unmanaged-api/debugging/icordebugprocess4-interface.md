---
title: Интерфейс ICorDebugProcess4
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: fcf725ea98fa4351e72cf592f92968ee2233ecb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213586"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="da242-102">Интерфейс ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="da242-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="da242-103">Обеспечивает поддержку управления выполнением в процессе.</span><span class="sxs-lookup"><span data-stu-id="da242-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="da242-104">Методы</span><span class="sxs-lookup"><span data-stu-id="da242-104">Methods</span></span>

| <span data-ttu-id="da242-105">Метод</span><span class="sxs-lookup"><span data-stu-id="da242-105">Method</span></span>                                                                 | <span data-ttu-id="da242-106">Описание</span><span class="sxs-lookup"><span data-stu-id="da242-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="da242-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="da242-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="da242-108">Уведомляет конвейер ICorDebug о том, что отладчик out-Process продолжает выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="da242-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="da242-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="da242-109">Remarks</span></span>

<span data-ttu-id="da242-110">Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="da242-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="da242-111">Однако это COM-интерфейс, производный от `IUnknown` GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` , который можно получить с помощью стандартных механизмов com.</span><span class="sxs-lookup"><span data-stu-id="da242-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="da242-112">Требования</span><span class="sxs-lookup"><span data-stu-id="da242-112">Requirements</span></span>

<span data-ttu-id="da242-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da242-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="da242-114">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="da242-114">**Header:** None</span></span>

<span data-ttu-id="da242-115">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="da242-115">**Library:** None</span></span>

<span data-ttu-id="da242-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da242-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="da242-117">См. также</span><span class="sxs-lookup"><span data-stu-id="da242-117">See also</span></span>

- [<span data-ttu-id="da242-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="da242-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="da242-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="da242-119">Debugging</span></span>](index.md)
