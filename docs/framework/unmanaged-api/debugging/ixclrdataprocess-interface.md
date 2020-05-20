---
title: Интерфейс IXCLRDataProcess
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 6a6def8fc10f04b89aa8d8c735025b01f9b6ddfb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420764"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="f1f9b-102">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="f1f9b-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="f1f9b-103">Предоставляет методы для запроса сведений о процессе.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="f1f9b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f1f9b-104">Methods</span></span>

| <span data-ttu-id="f1f9b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f1f9b-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="f1f9b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f1f9b-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="f1f9b-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="f1f9b-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="f1f9b-108">Возвращает `AppDomain` в процессе по его уникальному идентификатору.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="f1f9b-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="f1f9b-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="f1f9b-110">Предоставляет описатель для перечисления модулей процесса.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="f1f9b-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="f1f9b-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="f1f9b-112">Перечисляет модули этого процесса.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="f1f9b-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="f1f9b-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="f1f9b-114">Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении модулей.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="f1f9b-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="f1f9b-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="f1f9b-116">Предоставляет описатель для перечисления экземпляров методов, `AppDomain` начиная с заданного адреса.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="f1f9b-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="f1f9b-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="f1f9b-118">Перечисляет экземпляры методов этого процесса, начиная с смещения адреса.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="f1f9b-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="f1f9b-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="f1f9b-120">Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="f1f9b-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f1f9b-121">Remarks</span></span>

<span data-ttu-id="f1f9b-122">Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="f1f9b-123">Однако это COM-интерфейс, производный от `IUnknown` GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` , который можно получить с помощью стандартных механизмов com.</span><span class="sxs-lookup"><span data-stu-id="f1f9b-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1f9b-124">Требования</span><span class="sxs-lookup"><span data-stu-id="f1f9b-124">Requirements</span></span>

<span data-ttu-id="f1f9b-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1f9b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="f1f9b-126">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="f1f9b-126">**Header:** None</span></span>  
<span data-ttu-id="f1f9b-127">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="f1f9b-127">**Library:** None</span></span>  
<span data-ttu-id="f1f9b-128">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f9b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f1f9b-129">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f1f9b-129">See also</span></span>

- [<span data-ttu-id="f1f9b-130">Отладка</span><span class="sxs-lookup"><span data-stu-id="f1f9b-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="f1f9b-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f1f9b-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
