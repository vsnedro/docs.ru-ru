---
title: 'Метод Иксклрдатамесоддефинитион:: Енуминстанце'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ae1ef2a3c8cf9e042ab9ab233ed993f8e36b2fce
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420946"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="138fe-102">Метод Иксклрдатамесоддефинитион:: Енуминстанце</span><span class="sxs-lookup"><span data-stu-id="138fe-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="138fe-103">Перечисляет экземпляры этого определения метода.</span><span class="sxs-lookup"><span data-stu-id="138fe-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="138fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="138fe-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="138fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="138fe-105">Parameters</span></span>

`handle`\
<span data-ttu-id="138fe-106">[вход, выход] Маркер для перечисления экземпляров.</span><span class="sxs-lookup"><span data-stu-id="138fe-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="138fe-107">заполняет Перечислимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="138fe-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="138fe-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="138fe-108">Remarks</span></span>

<span data-ttu-id="138fe-109">Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует шестому слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="138fe-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="138fe-110">Требования</span><span class="sxs-lookup"><span data-stu-id="138fe-110">Requirements</span></span>

<span data-ttu-id="138fe-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="138fe-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="138fe-112">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="138fe-112">**Header:** None</span></span>  
<span data-ttu-id="138fe-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="138fe-113">**Library:** None</span></span>  
<span data-ttu-id="138fe-114">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="138fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="138fe-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="138fe-115">See also</span></span>

- [<span data-ttu-id="138fe-116">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="138fe-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="138fe-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="138fe-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="138fe-118">Интерфейс IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="138fe-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="138fe-119">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="138fe-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
