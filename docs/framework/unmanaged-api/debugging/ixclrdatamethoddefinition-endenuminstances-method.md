---
title: 'Метод Иксклрдатамесоддефинитион:: Енденуминстанцес'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7271c9594a679af205c404f59ff6731821aa0acf
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420998"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="578d8-102">Метод Иксклрдатамесоддефинитион:: Енденуминстанцес</span><span class="sxs-lookup"><span data-stu-id="578d8-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="578d8-103">Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.</span><span class="sxs-lookup"><span data-stu-id="578d8-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="578d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="578d8-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="578d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="578d8-105">Parameters</span></span>

`handle`\
<span data-ttu-id="578d8-106">заполняет Маркер для перечисления экземпляров.</span><span class="sxs-lookup"><span data-stu-id="578d8-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="578d8-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="578d8-107">Remarks</span></span>

<span data-ttu-id="578d8-108">Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует седьмому слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="578d8-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="578d8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="578d8-109">Requirements</span></span>

<span data-ttu-id="578d8-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="578d8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="578d8-111">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="578d8-111">**Header:** None</span></span>  
<span data-ttu-id="578d8-112">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="578d8-112">**Library:** None</span></span>  
<span data-ttu-id="578d8-113">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="578d8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="578d8-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="578d8-114">See also</span></span>

- [<span data-ttu-id="578d8-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="578d8-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="578d8-116">Интерфейс IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="578d8-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
