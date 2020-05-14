---
title: 'Метод Иксклрдатамесоддефинитион:: Стартенуминстанцес'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 84e0ad392c5fee8377115427482d80543454fff3
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397210"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="99fba-102">Метод Иксклрдатамесоддефинитион:: Стартенуминстанцес</span><span class="sxs-lookup"><span data-stu-id="99fba-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="99fba-103">Предоставляет обработчик для перечисления экземпляров методов для заданного объекта `IXCLRDataAppDomain` .</span><span class="sxs-lookup"><span data-stu-id="99fba-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="99fba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99fba-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="99fba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99fba-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="99fba-106">окне Домен приложения для перечисления.</span><span class="sxs-lookup"><span data-stu-id="99fba-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="99fba-107">заполняет Маркер для перечисления экземпляров.</span><span class="sxs-lookup"><span data-stu-id="99fba-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="99fba-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="99fba-108">Remarks</span></span>

<span data-ttu-id="99fba-109">Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует 5-сегменту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="99fba-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="99fba-110">Требования</span><span class="sxs-lookup"><span data-stu-id="99fba-110">Requirements</span></span>

<span data-ttu-id="99fba-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99fba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="99fba-112">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="99fba-112">**Header:** None</span></span>  
<span data-ttu-id="99fba-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="99fba-113">**Library:** None</span></span>  
<span data-ttu-id="99fba-114">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="99fba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="99fba-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="99fba-115">See also</span></span>

- [<span data-ttu-id="99fba-116">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="99fba-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="99fba-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="99fba-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="99fba-118">Интерфейс IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="99fba-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
