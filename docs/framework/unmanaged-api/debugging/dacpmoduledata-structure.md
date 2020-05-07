---
title: Структура DacpModuleData
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: e10d1792a8dc0b57ddd121ec09854e8e1824cade
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860799"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="0b111-102">Структура DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="0b111-102">DacpModuleData Structure</span></span>

<span data-ttu-id="0b111-103">Определяет транспортный буфер для сведений о среде выполнения модуля.</span><span class="sxs-lookup"><span data-stu-id="0b111-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0b111-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b111-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="0b111-105">Члены</span><span class="sxs-lookup"><span data-stu-id="0b111-105">Members</span></span>

| <span data-ttu-id="0b111-106">Участник</span><span class="sxs-lookup"><span data-stu-id="0b111-106">Member</span></span>    | <span data-ttu-id="0b111-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0b111-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="0b111-108">Адрес объекта модуля.</span><span class="sxs-lookup"><span data-stu-id="0b111-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="0b111-109">Указатель на переносимый исполняемый файл (PE).</span><span class="sxs-lookup"><span data-stu-id="0b111-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="0b111-110">Адрес базы загруженного образа.</span><span class="sxs-lookup"><span data-stu-id="0b111-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="0b111-111">Буфер полезных данных для дополнительных сведений о модулях, используемых средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="0b111-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0b111-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b111-112">Remarks</span></span>

<span data-ttu-id="0b111-113">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="0b111-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0b111-114">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="0b111-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b111-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0b111-115">Requirements</span></span>
<span data-ttu-id="0b111-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b111-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0b111-117">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="0b111-117">**Header:** None</span></span>  
<span data-ttu-id="0b111-118">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="0b111-118">**Library:** None</span></span>  
<span data-ttu-id="0b111-119">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0b111-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0b111-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0b111-120">See also</span></span>

- [<span data-ttu-id="0b111-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="0b111-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="0b111-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="0b111-122">Debugging Structures</span></span>](debugging-structures.md)
