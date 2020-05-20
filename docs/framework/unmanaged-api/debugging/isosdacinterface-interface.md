---
title: Интерфейс ISOSDacInterface
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c9b4e6e5b36fe38b6c0ea78f6d1848d155008bcc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420972"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="27a97-102">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="27a97-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="27a97-103">Предоставляет вспомогательные методы для доступа к данным из `SOS` .</span><span class="sxs-lookup"><span data-stu-id="27a97-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="27a97-104">Методы</span><span class="sxs-lookup"><span data-stu-id="27a97-104">Methods</span></span>

| <span data-ttu-id="27a97-105">Метод</span><span class="sxs-lookup"><span data-stu-id="27a97-105">Method</span></span>                                                                                                               | <span data-ttu-id="27a97-106">Описание</span><span class="sxs-lookup"><span data-stu-id="27a97-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="27a97-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="27a97-107">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="27a97-108">Возвращает данные для заданного указателя MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="27a97-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="27a97-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="27a97-109">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="27a97-110">Получает указатель MethodDesc, соответствующий методу, содержащему указанный адрес собственной инструкции.</span><span class="sxs-lookup"><span data-stu-id="27a97-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="27a97-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="27a97-111">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="27a97-112">Извлекает данные, соответствующие модулю, загруженному по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="27a97-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="27a97-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="27a97-113">Remarks</span></span>

<span data-ttu-id="27a97-114">Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="27a97-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="27a97-115">Однако это COM-интерфейс, производный от `IUnknown` GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` , который можно получить с помощью стандартных механизмов com.</span><span class="sxs-lookup"><span data-stu-id="27a97-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="27a97-116">Требования</span><span class="sxs-lookup"><span data-stu-id="27a97-116">Requirements</span></span>

<span data-ttu-id="27a97-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27a97-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="27a97-118">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="27a97-118">**Header:** None</span></span>  
<span data-ttu-id="27a97-119">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="27a97-119">**Library:** None</span></span>  
<span data-ttu-id="27a97-120">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="27a97-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="27a97-121">См. также статью</span><span class="sxs-lookup"><span data-stu-id="27a97-121">See also</span></span>

- [<span data-ttu-id="27a97-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="27a97-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="27a97-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="27a97-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
