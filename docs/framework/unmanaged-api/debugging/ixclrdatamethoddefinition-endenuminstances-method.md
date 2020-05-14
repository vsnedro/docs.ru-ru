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
ms.openlocfilehash: febe6766c7a35228820421eee975c777988efd1f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396490"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="2982f-102">Метод Иксклрдатамесоддефинитион:: Енденуминстанцес</span><span class="sxs-lookup"><span data-stu-id="2982f-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="2982f-103">Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2982f-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2982f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2982f-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="2982f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2982f-105">Parameters</span></span>

`handle`\
<span data-ttu-id="2982f-106">заполняет Маркер для перечисления экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2982f-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="2982f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2982f-107">Remarks</span></span>

<span data-ttu-id="2982f-108">Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует седьмому слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="2982f-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2982f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2982f-109">Requirements</span></span>

<span data-ttu-id="2982f-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2982f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2982f-111">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="2982f-111">**Header:** None</span></span>  
<span data-ttu-id="2982f-112">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="2982f-112">**Library:** None</span></span>  
<span data-ttu-id="2982f-113">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2982f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2982f-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="2982f-114">See also</span></span>

- [<span data-ttu-id="2982f-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="2982f-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="2982f-116">Интерфейс IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="2982f-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
