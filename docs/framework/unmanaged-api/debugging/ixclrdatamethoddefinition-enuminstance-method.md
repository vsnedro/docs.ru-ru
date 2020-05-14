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
ms.openlocfilehash: 72560de9777b2d826418e63b4a4fcccf1e4fa8b9
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396482"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="ff7d4-102">Метод Иксклрдатамесоддефинитион:: Енуминстанце</span><span class="sxs-lookup"><span data-stu-id="ff7d4-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="ff7d4-103">Перечисляет экземпляры этого определения метода.</span><span class="sxs-lookup"><span data-stu-id="ff7d4-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ff7d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff7d4-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="ff7d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff7d4-105">Parameters</span></span>

`handle`\
<span data-ttu-id="ff7d4-106">[вход, выход] Маркер для перечисления экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ff7d4-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="ff7d4-107">заполняет Перечислимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ff7d4-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff7d4-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff7d4-108">Remarks</span></span>

<span data-ttu-id="ff7d4-109">Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует шестому слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="ff7d4-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff7d4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ff7d4-110">Requirements</span></span>

<span data-ttu-id="ff7d4-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff7d4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ff7d4-112">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="ff7d4-112">**Header:** None</span></span>  
<span data-ttu-id="ff7d4-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="ff7d4-113">**Library:** None</span></span>  
<span data-ttu-id="ff7d4-114">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ff7d4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ff7d4-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ff7d4-115">See also</span></span>

- [<span data-ttu-id="ff7d4-116">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="ff7d4-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="ff7d4-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="ff7d4-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="ff7d4-118">Интерфейс IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="ff7d4-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="ff7d4-119">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="ff7d4-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
