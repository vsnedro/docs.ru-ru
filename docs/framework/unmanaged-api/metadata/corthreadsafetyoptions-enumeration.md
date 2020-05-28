---
title: Перечисление CorThreadSafetyOptions
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
ms.openlocfilehash: 8c0527a7bc3cde7344bf809dc8e6f5a3fac04852
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007511"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="c4071-102">Перечисление CorThreadSafetyOptions</span><span class="sxs-lookup"><span data-stu-id="c4071-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="c4071-103">Задает флаги для выбора параметров безопасности потока.</span><span class="sxs-lookup"><span data-stu-id="c4071-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="c4071-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4071-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="c4071-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c4071-105">Members</span></span>

|<span data-ttu-id="c4071-106">Член</span><span class="sxs-lookup"><span data-stu-id="c4071-106">Member</span></span>|<span data-ttu-id="c4071-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c4071-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="c4071-108">Значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c4071-108">Default value.</span></span> <span data-ttu-id="c4071-109">Эквивалентно `MDThreadSafetyOff`.</span><span class="sxs-lookup"><span data-stu-id="c4071-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="c4071-110">Указывает, что невозможно установить блокировку потоков чтения/записи.</span><span class="sxs-lookup"><span data-stu-id="c4071-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="c4071-111">Указывает, что можно задать блокировку потоков чтения/записи.</span><span class="sxs-lookup"><span data-stu-id="c4071-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="c4071-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c4071-112">Requirements</span></span>

<span data-ttu-id="c4071-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4071-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c4071-114">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="c4071-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="c4071-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4071-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c4071-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c4071-116">See also</span></span>

- [<span data-ttu-id="c4071-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="c4071-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
