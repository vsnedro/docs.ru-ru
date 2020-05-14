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
ms.openlocfilehash: e28fa73300e147ac07a2d325fbf517480bb73797
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394938"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="6c9a7-102">Метод Иксклрдатапроцесс:: Стартенуммесодинстанцесбяддресс</span><span class="sxs-lookup"><span data-stu-id="6c9a7-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="6c9a7-103">Предоставляет описатель для перечисления экземпляров методов, `AppDomain` начиная с заданного адреса.</span><span class="sxs-lookup"><span data-stu-id="6c9a7-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6c9a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c9a7-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="6c9a7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c9a7-105">Parameters</span></span>

`address`\
<span data-ttu-id="6c9a7-106">окне Адрес первого экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="6c9a7-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="6c9a7-107">окне AppDomain экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="6c9a7-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="6c9a7-108">заполняет Описатель для перечисления экземпляров методов.</span><span class="sxs-lookup"><span data-stu-id="6c9a7-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c9a7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6c9a7-109">Remarks</span></span>

<span data-ttu-id="6c9a7-110">Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует 28-го слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="6c9a7-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6c9a7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6c9a7-111">Requirements</span></span>

<span data-ttu-id="6c9a7-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c9a7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6c9a7-113">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="6c9a7-113">**Header:** None</span></span>  
<span data-ttu-id="6c9a7-114">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="6c9a7-114">**Library:** None</span></span>  
<span data-ttu-id="6c9a7-115">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6c9a7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6c9a7-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="6c9a7-116">See also</span></span>

- [<span data-ttu-id="6c9a7-117">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="6c9a7-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="6c9a7-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="6c9a7-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="6c9a7-119">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="6c9a7-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
