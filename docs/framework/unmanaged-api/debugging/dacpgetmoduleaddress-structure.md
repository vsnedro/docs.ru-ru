---
title: Структура DacpGetModuleAddress
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e460264e2393858c028ba51aec4a4f2c01649994
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860824"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="f12e9-102">Структура DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="f12e9-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="f12e9-103">Определяет контейнер для запроса адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="f12e9-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f12e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f12e9-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="f12e9-105">Члены</span><span class="sxs-lookup"><span data-stu-id="f12e9-105">Members</span></span>

| <span data-ttu-id="f12e9-106">Участник</span><span class="sxs-lookup"><span data-stu-id="f12e9-106">Member</span></span>      | <span data-ttu-id="f12e9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f12e9-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="f12e9-108">Указатель на модуль.</span><span class="sxs-lookup"><span data-stu-id="f12e9-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="f12e9-109">Методы</span><span class="sxs-lookup"><span data-stu-id="f12e9-109">Methods</span></span>

| <span data-ttu-id="f12e9-110">Метод</span><span class="sxs-lookup"><span data-stu-id="f12e9-110">Method</span></span>                                                                                               | <span data-ttu-id="f12e9-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f12e9-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="f12e9-112">Запрос</span><span class="sxs-lookup"><span data-stu-id="f12e9-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="f12e9-113">Выполняет запрос на заполнение структуры из заданной структуры среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f12e9-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f12e9-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="f12e9-114">Remarks</span></span>

<span data-ttu-id="f12e9-115">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="f12e9-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="f12e9-116">Чтобы использовать его, определите структуру, как указано выше, где `CLRDATA_ADDRESS` — это 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="f12e9-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="f12e9-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f12e9-117">Requirements</span></span>
<span data-ttu-id="f12e9-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f12e9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f12e9-119">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="f12e9-119">**Header:** None</span></span>  
<span data-ttu-id="f12e9-120">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="f12e9-120">**Library:** None</span></span>  
<span data-ttu-id="f12e9-121">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f12e9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f12e9-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f12e9-122">See also</span></span>

- [<span data-ttu-id="f12e9-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="f12e9-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="f12e9-124">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="f12e9-124">Debugging Structures</span></span>](debugging-structures.md)
