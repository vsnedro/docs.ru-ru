---
title: 'Метод Иксклрдатапроцесс:: Стартенуммесодинстанцесбяддресс'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 52d533f1c86b34b7b9febade8590e7ab58d8221e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420739"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="434de-102">Метод Иксклрдатапроцесс:: Стартенуммесодинстанцесбяддресс</span><span class="sxs-lookup"><span data-stu-id="434de-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="434de-103">Предоставляет описатель для перечисления экземпляров методов, `AppDomain` начиная с заданного адреса.</span><span class="sxs-lookup"><span data-stu-id="434de-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="434de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="434de-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="434de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="434de-105">Parameters</span></span>

`address`\
<span data-ttu-id="434de-106">окне Адрес первого экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="434de-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="434de-107">окне AppDomain экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="434de-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="434de-108">заполняет Описатель для перечисления экземпляров методов.</span><span class="sxs-lookup"><span data-stu-id="434de-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="434de-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="434de-109">Remarks</span></span>

<span data-ttu-id="434de-110">Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует 28-го слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="434de-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="434de-111">Требования</span><span class="sxs-lookup"><span data-stu-id="434de-111">Requirements</span></span>

<span data-ttu-id="434de-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="434de-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="434de-113">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="434de-113">**Header:** None</span></span>  
<span data-ttu-id="434de-114">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="434de-114">**Library:** None</span></span>  
<span data-ttu-id="434de-115">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="434de-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="434de-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="434de-116">See also</span></span>

- [<span data-ttu-id="434de-117">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="434de-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="434de-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="434de-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="434de-119">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="434de-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
