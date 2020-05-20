---
title: Интерфейс IXCLRDataModule
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3c2bc771c0a131329b9403c99a33ca7b79023771
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420855"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="03e89-102">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="03e89-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="03e89-103">Предоставляет методы для запроса сведений о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="03e89-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="03e89-104">Методы</span><span class="sxs-lookup"><span data-stu-id="03e89-104">Methods</span></span>

| <span data-ttu-id="03e89-105">Метод</span><span class="sxs-lookup"><span data-stu-id="03e89-105">Method</span></span>                                                                                                                                | <span data-ttu-id="03e89-106">Описание</span><span class="sxs-lookup"><span data-stu-id="03e89-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="03e89-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="03e89-107">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="03e89-108">Возвращает определение метода, соответствующее заданному маркеру метаданных.</span><span class="sxs-lookup"><span data-stu-id="03e89-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="03e89-109">Получения</span><span class="sxs-lookup"><span data-stu-id="03e89-109">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="03e89-110">Запросы на заполнение буфера данными модуля.</span><span class="sxs-lookup"><span data-stu-id="03e89-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="03e89-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="03e89-111">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="03e89-112">Возвращает идентификатор версии модуля.</span><span class="sxs-lookup"><span data-stu-id="03e89-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="03e89-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="03e89-113">Remarks</span></span>

<span data-ttu-id="03e89-114">Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="03e89-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="03e89-115">Однако это COM-интерфейс, производный от `IUnknown` GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` , который можно получить с помощью стандартных механизмов com.</span><span class="sxs-lookup"><span data-stu-id="03e89-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="03e89-116">Требования</span><span class="sxs-lookup"><span data-stu-id="03e89-116">Requirements</span></span>

<span data-ttu-id="03e89-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03e89-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="03e89-118">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="03e89-118">**Header:** None</span></span>  
<span data-ttu-id="03e89-119">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="03e89-119">**Library:** None</span></span>  
<span data-ttu-id="03e89-120">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="03e89-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="03e89-121">См. также статью</span><span class="sxs-lookup"><span data-stu-id="03e89-121">See also</span></span>

- [<span data-ttu-id="03e89-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="03e89-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="03e89-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="03e89-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
