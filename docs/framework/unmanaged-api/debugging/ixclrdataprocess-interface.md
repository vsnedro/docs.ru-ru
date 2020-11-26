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
ms.openlocfilehash: 376ec2b840bc17c79ed1f27c17a8ddd22c37a0f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245358"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="8b3ef-102">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="8b3ef-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="8b3ef-103">Предоставляет методы для запроса сведений о процессе.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="8b3ef-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8b3ef-104">Methods</span></span>

| <span data-ttu-id="8b3ef-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8b3ef-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="8b3ef-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8b3ef-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="8b3ef-107">жетрунтименамебяддресс</span><span class="sxs-lookup"><span data-stu-id="8b3ef-107">GetRuntimeNameByAddress</span></span>](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | <span data-ttu-id="8b3ef-108">Возвращает имя для заданного адреса.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-108">Gets a name for the given address.</span></span>                                                               |
| [<span data-ttu-id="8b3ef-109">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="8b3ef-109">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="8b3ef-110">Возвращает `AppDomain` в процессе по его уникальному идентификатору.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-110">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="8b3ef-111">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="8b3ef-111">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="8b3ef-112">Предоставляет описатель для перечисления модулей процесса.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-112">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="8b3ef-113">EnumModule</span><span class="sxs-lookup"><span data-stu-id="8b3ef-113">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="8b3ef-114">Перечисляет модули этого процесса.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-114">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="8b3ef-115">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="8b3ef-115">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="8b3ef-116">Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении модулей.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-116">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="8b3ef-117">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="8b3ef-117">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="8b3ef-118">Предоставляет описатель для перечисления экземпляров методов, `AppDomain` начиная с заданного адреса.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-118">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="8b3ef-119">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="8b3ef-119">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="8b3ef-120">Перечисляет экземпляры методов этого процесса, начиная с смещения адреса.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-120">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="8b3ef-121">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="8b3ef-121">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="8b3ef-122">Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-122">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="8b3ef-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b3ef-123">Remarks</span></span>

<span data-ttu-id="8b3ef-124">Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-124">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8b3ef-125">Однако это COM-интерфейс, производный от `IUnknown` GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` , который можно получить с помощью стандартных механизмов com.</span><span class="sxs-lookup"><span data-stu-id="8b3ef-125">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b3ef-126">Требования</span><span class="sxs-lookup"><span data-stu-id="8b3ef-126">Requirements</span></span>

<span data-ttu-id="8b3ef-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b3ef-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="8b3ef-128">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="8b3ef-128">**Header:** None</span></span>  
<span data-ttu-id="8b3ef-129">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="8b3ef-129">**Library:** None</span></span>  
<span data-ttu-id="8b3ef-130">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8b3ef-130">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8b3ef-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8b3ef-131">See also</span></span>

- [<span data-ttu-id="8b3ef-132">Отладка</span><span class="sxs-lookup"><span data-stu-id="8b3ef-132">Debugging</span></span>](index.md)
- [<span data-ttu-id="8b3ef-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8b3ef-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
